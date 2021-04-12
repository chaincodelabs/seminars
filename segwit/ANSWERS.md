# Some Responses to the Discussion Questions

Q: How is ECDSA malleable?  
A: Signing through ECDSA only uses the x coordinate in its values so if s is a valid signature, so is -s. This is still considered an unforgeable signature, i.e. you can’t produce a valid signature on a different message without the private key, malleability isn’t a problem about correctness/security.

Q: Why do second layer protocols (like Lightning) require transaction malleability to be fixed?
A: Lighting is based on the principle of being able to lock down child transactions just in case a parent transaction is broadcast. You can spend from a parent by referring to its txid. It doesn't work if it changes.

Q: How can new script versions remain backwards compatible?  
A: TX version field for example is checked by `op_checksequenceverify`, a script op_code. The witness version is not checked by a script operator, but pushed onto the stack and evaluated at the end of the script run, when the witness script pattern is detected. I suppose it would entirely be possible to encode the witness version in the version field as well.

Q: What is weight versus virtual bytes? How do they differ? How does weight change the relative costs of inputs and outputs?  
A: Weight units are a measurement used to compare the size of different Bitcoin transactions to each other in proportion to the consensus-enforced maximum block size limit. Virtual size (vsize), also called virtual bytes (vbytes), are an alternative measurement, with one vbyte being equal to four weight units ([source](https://en.bitcoin.it/wiki/Weight_units#:~:text=Weight%20units%20are%20a%20measurement,enforced%20maximum%20block%20size%20limit.&text=Virtual%20size%20(vsize)%2C%20also,equal%20to%20four%20weight%20units.)). vBytes let us think of cost in linear terms, while embedding the asymmetry of costs of RAM and disk in the formula as well helping when mixing TXin and TXout types. The concept of weight does not make sense to older wallets so we describe in vbytes (older nodes would just call these bytes). Segwit does not make transactions smaller (in terms of total size and how much data you need to transmit over the p2p network), but does reduce an individual transaction’s effective size on-chain.

Q: What rationale was used to decide on the 4 MB SegWit block weight (3 x old_tx_bytes + segwit_tx_bytes), instead of say a 2 MB block weight (old_tx_bytes + segwit_tx_bytes)?  
A: The factor of 4 helps to create more of a balance between the cost of creating an output and the cost of spending an output. In typical transaction data, an output can be created using around 32 bytes, but spending it requires around 108 bytes. With the old metric, every byte of data you included in a transaction increased its fee. So, as a result, it cost more to spend an output than it did to create one. However, by using the new weight metric, there is more of an even balance between the cost of creating an output and spending an output ([source](https://learnmeabitcoin.com/technical/transaction-weight)). This ultimately corrected the misalignment of incentives that would have likely led to more UTXO bloat.

Q: How do blocks commit to witness data?  
A: SegWit nodes require a new commitment to the block's coinbase transaction, if any SegWit transactions are found in the block. This commitment is recorded in a `scriptPubKey` using a double-sha256 hash of the witness root hash (a merkle root of all of `wtxid`s) and the witness reserved value (a reserved value that can be used for SegWit upgrades in the future).

Q: What is the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this?  
A: Verification includes hashing, and amount of hashing is proportional to the size of the transaction. A specially crafted transaction could take minutes to verify. Explanation by [Sipa](https://youtu.be/NOYNZB5BCHM?t=1625).

Q: Where are the locking script operations in P2WPKH/P2WSH?  
A: Non-witness nodes never receive any witness data or witness blocks (BIP144), and only validate the spending of [0 20/32b-hash] witness script (no witness data is available and is not evaluated). The correctness of a witness spend therefore differs between old/new nodes. If the strong-chain is a witness chain, it is safe to assume old nodes will follow this chain, and the correctness of witness transactions is implied by POW for these older nodes. If the strong-chain is not a witness chain, new nodes will fork off (weak-chain), but old nodes will continue to follow it. It is not safe to conduct witness transactions on this non-witness strong-chain. This is why miner-support for SegWit is relevant during activation.

Q: [optional] What are some address format design goals and requirements discussed in the bech32 talk? How problematic is the bech32 mutability issue for v0 segwit addresses versus for taproot?  
A: See [bech32 mutability](https://bitcoinops.org/en/newsletters/2019/12/28/#bech32-mutability) write-up for more info.
