# SegWit

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
| [What is SegWit?](https://bitcoinmagazine.com/guides/what-is-segwit) | 5 min | primer                  |
| [SegWit in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc#segregated-witness) or [SegWit with Jimmy Song](https://www.youtube.com/watch?v=Txfy2mFe16A) | 30 min | segwit |
| [SegWit's Impact on Scalability](https://diyhpl.us/wiki/transcripts/scalingbitcoin/hong-kong/segregated-witness-and-its-impact-on-scalability/) | 30 min | 2015, scale |
| [The Long Road to SegWit](https://bitcoinmagazine.com/articles/long-road-segwit-how-bitcoins-biggest-protocol-upgrade-became-reality/) | 20 min | history |
| [Advanced SegWit](https://www.youtube.com/watch?v=JgNgnwF9hfY) | 90 min | advanced, video |
| [SegWit Benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) | 12 min | technical |
| [SegWit Costs](https://bitcoincore.org/en/2016/10/28/segwit-costs/) | 20 min | technical |
| [2015 Malleability Attack](https://bitcoinmagazine.com/articles/the-who-what-why-and-how-of-the-ongoing-transaction-malleability-attack-1444253640/) | 10 min | malleability, attack vectors |
| [BIP 62](https://github.com/bitcoin/bips/blob/master/bip-0062.mediawiki) | 15 min | malleability, bitcoin archaeology |
| [Bech32](https://diyhpl.us/wiki/transcripts/sf-bitcoin-meetup/2017-03-29-new-address-type-for-segwit-addresses/) | 35 min video | bech32, *optional* |
| [SegWit Wallet Development](https://bitcoincore.org/en/segwit_wallet_dev/) | 10 min | wallet, *optional* |
| [Code Walkthrough](https://docs.google.com/document/d/1qn9SCQj2YQauE83FjglODUZJTQaz9WxrbaTtkP367cA/edit) | 20 min | code, *optional* |
| [Code Review: The Consensus Critical Parts of Segwit](https://petertodd.org/2016/segwit-consensus-critical-code-review) | 30 min | code, *optional* |

## Discussion Questions

1. How is ECDSA malleable?
1. Why do second layer protocols (like Lightning) require transaction malleability to be fixed?
1. How should one understand anyone-can-spend outputs? Do nodes with and without the SegWit upgrade behave differently while validating enforcing? How?
1. How do the SegWit script versions conceptually differ from the versions on transactions? Why couldn't the transaction versions be used to support newer functionality without hard forks?
1. How does new script versions remain backwards compatible?
1. What is weight versus virtual bytes? How do they differ?
1. What rationale was used to decide on the 4 MB SegWit block weight (3 x old_tx_bytes + segwit_tx_bytes), instead of say a 2 MB block weight (old_tx_bytes + segwit_tx_bytes)?
1. How is witness data committed to the block?
1. What was the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this?
1. How did users know whether miners support SegWit prior to activation?
1. How does a (virtual block increase) affect IBD cost over time?
1. Where are the locking script operations in P2WPKH/P2WSH?
1. [optional] What are some address format design goals and requirements discussed in the bech32 talk? How problematic is the bech32 mutability issue for v0 segwit addresses versus for taproot?
