# SegWit

## Reading

| Content                                                            | Time (min)      |
|--------------------------------------------------------------------|-----------------|
| [What is SegWit?](https://bitcoinmagazine.com/guides/what-is-segwit) | 5 |
| [SegWit in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc#segregated-witness) or [SegWit video w/ Jimmy Song](https://www.youtube.com/watch?v=Txfy2mFe16A) | 30 |
| [SegWit Benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) | 12 |
| [Transaction Malleability](https://eklitzke.org/bitcoin-transaction-malleability) | 15 |
| [SegWit's Impact on Scalability](https://diyhpl.us/wiki/transcripts/scalingbitcoin/hong-kong/segregated-witness-and-its-impact-on-scalability/) | 30 |
| [Advanced SegWit w/ James O'Beirne](http://diyhpl.us/wiki/transcripts/chaincode-labs/2019-06-18-james-obeirne-advanced-segwit/) | 60 |
| [SegWit Costs](https://bitcoincore.org/en/2016/10/28/segwit-costs/) | 20 |
| [The Long Road to SegWit](https://bitcoinmagazine.com/articles/long-road-segwit-how-bitcoins-biggest-protocol-upgrade-became-reality/) | 20 |
| (_optional_) [Bech32](https://diyhpl.us/wiki/transcripts/sf-bitcoin-meetup/2017-03-29-new-address-type-for-segwit-addresses/) | 35 |
| [SegWit Wallet Development](https://bitcoincore.org/en/segwit_wallet_dev/) | 10 |

## Discussion Questions

### What is SegWit?

1. Is a non-segwit node considered a full node?
1. What is the difference between a hard and soft fork?

### SegWit in Mastering Bitcoin / SegWit video w/ Jimmy Song

1. How should one understand ANYONE_CAN_SPEND outputs? Do nodes with and without the SegWit upgrade behave differently while validating or enforcing?
1. [Optional] What is the difference between wrapped SegWit and native SegWit addresses? (SegWit Wallet Development)

### Transaction Malleability

1. How is ECDSA malleable?

### SegWit Benefits
1. Why do second layer protocols (like Lightning) require transaction malleability to be fixed?

### Advanced SegWit

1. How do blocks commit to witness data?
1. What is weight versus virtual bytes? How do they differ? How does weight change the relative costs of inputs and outputs?
1. How could BIP 9 be considered controversial within the community? How was BIP 148 received when first proposed?

### SegWit's Impact on Scalability
1. What was the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this?
1. What rationale was used to decide on the 4 MB SegWit block weight (3 x old_tx_bytes + segwit_tx_bytes), instead of say a 2 MB block weight (old_tx_bytes + segwit_tx_bytes)?

### SegWit Costs

1. How does SegWit affect initial block download (IBD)?

### Gregory Maxwell’s Inhibition Proposal

1. What is ASIC BOOST and what did it have to do with SegWit's deployment?

### The Long Road to SegWit

1. How did users know whether miners support SegWit prior to activation?

### Bech32 (optional)

1. What are some address format design goals and requirements discussed in the bech32 talk? How problematic is the bech32 mutability issue for v0 segwit addresses versus for taproot?
