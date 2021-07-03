# Scripts and Wallets

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Bitcoin Script: Past and Future](https://btctranscripts.com/chaincode-labs/2020-04-08-john-newbery-contracts-in-bitcoin/) | 25 |
| [Script: A Mini Programming Language](https://learnmeabitcoin.com/technical/script) | 10 |
| [Scripts \(general & simple\)](https://btctranscripts.com/scalingbitcoin/tokyo-2018/edgedevplusplus/scripts-general-and-simple/) | 30 |
| [Miniscript: Streamlined Bitcoin Scripting](https://medium.com/blockstream/miniscript-bitcoin-scripting-3aeff3853620) | 11 |
| \(_optional_\) [Using the Chain for What Chains are Good For](https://btctranscripts.com/scalingbitcoin/stanford-2017/using-the-chain-for-what-chains-are-good-for/) | 25 |
| [HD Wallets](https://learnmeabitcoin.com/technical/hd-wallets) | 10 |
| [Coin Selection](https://btctranscripts.com/scalingbitcoin/tokyo-2018/edgedevplusplus/coin-selection/) | 20 |
| [An Introduction to Bitcoin Core Fee Estimation](https://bitcointechtalk.com/an-introduction-to-bitcoin-core-fee-estimation-27920880ad0) | 11 |
| [Fee Bumping and RBF](https://github.com/bitcoinops/scaling-book/blob/add_rbf/1.fee_bumping/fee_bumping.md) | 20 |
| \(_optional_\) [PSBT with Andrew Chow](https://btctranscripts.com/sf-bitcoin-meetup/2019-03-15-partially-signed-bitcoin-transactions) | 20 |
| \(_optional_\) Native Descriptor Wallets - [gist](https://gist.github.com/achow101/94d889715afd49181f8efdca1f9faa25) or [presentation](https://btctranscripts.com/advancing-bitcoin/2020/2020-02-06-andrew-chow-descriptor-wallets/) | 10 or 18 |


## Discussion Questions

### SCRIPT

1. John Newbery talks about [verification vs. computation](https://youtu.be/np-SCwkqVy4?t=934), and he bring it up as a big reason why he thinks bitcoin can scale but is skeptical about ethereum. Is there a qualitative difference between verification and computation? And is it the fact that ethereum is capable of performing arbitrary computation that makes the whole thing difficult to scale, or is it that specifically smart contracts that require arbitrary computation won’t be able to scale \(as in those contracts would be very expensive to run\)?

### Output Descriptors

1. What is the benefit of using output descriptors?
2. Are there any use cases for p2sh-wsh-p2pkh descriptors?
3. What's about miniscript? Interactions with descriptors?

### HD Wallets

1. What is the difference between child and hardened child addresses?
2. Why is the internal chain not visible outside of the wallet if it uses public derivation?

### Coin Selection

1. Is coin age ever a consideration for coin selection?
2. Coin selection can expose a wallet by observing how the wallet selects its inputs, are there any efforts to standardize coin selection into a library of sorts so there's a standard?

### Fee Bumping and RBF

1. Is there way to ensure that a transaction will be processed? What tools are available to ensure a stuck transaction \(due to low fees\) gets processed?
2. While inconvenient, could a stuck transaction lead to a loss of funds?

