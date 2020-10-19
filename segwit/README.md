# SegWit

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
| [What is SegWit?](https://bitcoinmagazine.com/guides/what-is-segwit) | 5 min | primer                  |
| [SegWit in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc#segregated-witness) or [SegWit video w/ Jimmy Song](https://www.youtube.com/watch?v=Txfy2mFe16A) | 30 min | foundations |
| [SegWit Benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) | 12 min | technical |
| [Transaction Malleability](https://eklitzke.org/bitcoin-transaction-malleability) | 15 min | 2017, malleability |
| [SegWit's Impact on Scalability](https://diyhpl.us/wiki/transcripts/scalingbitcoin/hong-kong/segregated-witness-and-its-impact-on-scalability/) | 30 min | 2015, scale |
| [SegWit Safari w/ James O'Beirne](http://diyhpl.us/wiki/transcripts/chaincode-labs/2019-06-18-james-obeirne-advanced-segwit/) | 60 min | segwit safari |
| [SegWit Costs](https://bitcoincore.org/en/2016/10/28/segwit-costs/) | 20 min | technical |
| [The Long Road to SegWit](https://bitcoinmagazine.com/articles/long-road-segwit-how-bitcoins-biggest-protocol-upgrade-became-reality/) | 20 min | history |
| [Bech32](https://diyhpl.us/wiki/transcripts/sf-bitcoin-meetup/2017-03-29-new-address-type-for-segwit-addresses/) | 35 min | bech32, *optional* |
| [SegWit Wallet Development](https://bitcoincore.org/en/segwit_wallet_dev/) | 10 min | wallet, *optional* |
| [Code Review: The Consensus Critical Parts of SegWit](https://petertodd.org/2016/segwit-consensus-critical-code-review) | 30 min | code, *optional* |

## Discussion Questions

1. Is a non-segwit node considered a full node?
1. What is the difference between a hard and soft fork? (SegWit in Mastering Bitcoin)
1. How is ECDSA malleable? (SegWit in Mastering Bitcoin)
1. Why do second layer protocols (like Lightning) require transaction malleability to be fixed? (SegWit in Mastering Bitcoin/SegWit Benefits)
1. How should one understand anyone-can-spend outputs? Do nodes with and without the SegWit upgrade behave differently while validating or enforcing? (SegWit in Mastering Bitcoin)
1. How does new script versions remain backwards compatible? How were script upgrades done in the past? (SegWit in Mastering Bitcoin/SegWit Benefits/Advanced SegWit)
1. How is witness data committed to the block? (SegWit in Mastering Bitcoin/Advanced SegWit)
1. What was the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this? (SegWit's Impact on Scalability/SegWit Benefits)
1. What is weight versus virtual bytes? How do they differ? How does weight change the relative costs of inputs and outputs? (Advanced SegWit)
1. What rationale was used to decide on the 4 MB SegWit block weight (3 x old_tx_bytes + segwit_tx_bytes), instead of say a 2 MB block weight (old_tx_bytes + segwit_tx_bytes)? (SegWit's Impact on Scalability/Advanced SegWit)
1. How does a virtual block increase affect IBD cost over time? (Advanced SegWit)
1. What is ASIC BOOST and what did it have to do with SegWit's deployment? (Gregory Maxwell’s Inhibition Proposal)
1. How could BIP 9 be considered controversial within the community? How was BIP 148 received when first proposed? (Advanced SegWit)
1. How did users know whether miners support SegWit prior to activation? (The Long Road to SegWit)
1. [Optional] What are some address format design goals and requirements discussed in the bech32 talk? How problematic is the bech32 mutability issue for v0 segwit addresses versus for taproot? (Bech32)
1. [Optional] What is the difference between wrapped SegWit and native SegWit addresses? (SegWit Wallet Development)
