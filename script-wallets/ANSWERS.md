# Some Responses to the Discussion Questions

Q: Is there a qualitative difference between verification and computation? And is it the fact that ethereum is capable of performing arbitrary computation that makes the whole thing difficult to scale, or is it that specifically smart contracts that require arbitrary computation won’t be able to scale (as in those contracts would be very expensive to run)?  
A: [A response](https://gist.github.com/adamjonas/84a5f8363d6f254f68202b62f6603608).

Q: Are there any use cases for p2sh-wsh-p2pkh descriptors?  
A: Extension to the descriptor language in Bitcoin Core for expressing all knowledge about how to spend a particular outputs. For more, see Pieter's talk on [Miniscript](http://diyhpl.us/wiki/transcripts/stanford-blockchain-conference/2019/miniscript/).

Q: What is the difference between child and hardened child addresses?  
A: Hardened private child keys are derived using the parent private key in the child derivation function and non-hardened private child keys are derived using the parent public keys. This leads to:

  1. Non-hardened public child keys can be derived from an extended public key without a private key being involved in the process. This is useful for a service like an e-commerce store. This is not possible for hardened keys since private keys are used.
  2. In case a non-hardened private child key is exposed together with the extended public key, that can be used to compromise the parent private key and all other private child keys. This is not possible with hardened key.
  
Additionally, note that non-hardened keys use child indexes from 1 to 2^31 -1 and hardened keys use 2^31 to 2^32 - 1. For more, see [BIP 32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki#Child_key_derivation_CKD_functions) and [Stack Exchange](https://bitcoin.stackexchange.com/questions/37488/eli5-whats-the-difference-between-a-child-key-and-a-hardened-child-key-in-bip3).

Q: Why is the internal chain not visible outside of the wallet if it uses public derivation?  
A: Corresponding external and internal chains are derived from one Account/Wallet. The external chain is used to derive addresses which can be shared with e.g. a buyer (ie somebody sending bitcoin). The internal chain is used to e.g.  derive a change address when sending bitcoin. Neither the external or internal chain are visible from outside of the wallet. The external chain can be shared e.g. via a public extended key (xpub) of that account/wallet. Then everybody, who has access to that xpub, can derive public keys for the external chain. As long as the xpub of the internal chain is not shared, it's not visible to the outside. See [BIP 32 (default wallet layout)](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki#the-default-wallet-layout), [BIP 32 (derivation graphic)](https://github.com/bitcoin/bips/raw/master/bip-0032/derivation.png), and [BIP 32 (Unsecure money receiver)](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki#unsecure-money-receiver-nmih0).
