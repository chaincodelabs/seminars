# Some Responses to the Discussion Questions

Q: How is ECDSA malleable?  
A: Signing through ECDSA only uses the x coordinate in its values so if s is a valid signature, so is -s. This is still considered an unforgeable signature, i.e. you can’t produce a valid signature on a different message without the private key, malleability isn’t a problem about correctness/security.

Q: Why do second layer protocols (like Lightning) require transaction malleability to be fixed?
A: Lighting is based on the principle of being able to lock down child transactions just in case a parent transaction is broadcast. You can spend from a parent by referring to its txid. It doesn't work if it changes.

Q: How can new script versions remain backwards compatible?  
A: TX version field for example is checked by `op_checksequenceverify`, a script op_code. The witness version is not checked by a script operator, but pushed onto the stack and evaluated at the end of the script run, when the witness script pattern is detected. I suppose it would entirely be possible to encode the witness version in the version field as well.

Q: What is weight versus virtual bytes? How do they differ?  
A: Weight units are a measurement used to compare the size of different Bitcoin transactions to each other in proportion to the consensus-enforced maximum block size limit. Virtual size (vsize), also called virtual bytes (vbytes), are an alternative measurement, with one vbyte being equal to four weight units ([source](https://en.bitcoin.it/wiki/Weight_units#:~:text=Weight%20units%20are%20a%20measurement,enforced%20maximum%20block%20size%20limit.&text=Virtual%20size%20(vsize)%2C%20also,equal%20to%20four%20weight%20units.)). Segwit does not make transactions smaller (in terms of total size and how much data you need to transmit over the p2p network), but does reduce an individual transaction’s effective size on-chain.

Q: How is witness data committed to the block?  
A: Witness program is a special type of scriptPubKey (locking script) that has a 1-byte push opcode (version byte) and then 2-40 byte data push.

Q: What is the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this?  
A: Verification includes hashing, and amount of hashing is proportional to the size of the transaction. A specially crafted transaction could take minutes to verify. Explanation by [Sipa](https://youtu.be/NOYNZB5BCHM?t=1625).

Q: Where are the locking script operations in P2WPKH/P2WSH?  
A: Non-witness nodes never receive any witness data or witness blocks (BIP144), and only validate the spending of [0 20/32b-hash] witness script (no witness data is available and is not evaluated). The correctness of a witness spend therefore differs between old/new nodes. If the strong-chain is a witness chain, it is safe to assume old nodes will follow this chain, and the correctness of witness transactions is implied by POW for these older nodes. If the strong-chain is not a witness chain, new nodes will fork off (weak-chain), but old nodes will continue to follow it. It is not safe to conduct witness transactions on this non-witness strong-chain. This is why miner-support for SegWit is relevant during activation.
