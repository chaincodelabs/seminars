# Scripts and Wallets

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Bitcoin Script: Past and Future](https://btctranscripts.com/misc/2020-04-08-john-newbery-contracts-in-bitcoin) | 35 |
| [Script: A Mini Programming Language](https://learnmeabitcoin.com/technical/script) | 15 |
| [Scripts \(general & simple\)](https://btctranscripts.com/scalingbitcoin/tokyo-2018/edgedevplusplus/scripts-general-and-simple/) | 40 |
| [Miniscript: Streamlined Bitcoin Scripting](https://medium.com/blockstream/miniscript-bitcoin-scripting-3aeff3853620) | 15 |
| \(_optional_\) [Using the Chain for What Chains are Good For](https://btctranscripts.com/scalingbitcoin/stanford-2017/using-the-chain-for-what-chains-are-good-for/) | 30 |
| [The Battle for P2SH](https://bitcoinmagazine.com/technical/the-battle-for-p2sh-the-untold-story-of-the-first-bitcoin-war) | 40 |
| [HD Wallets](https://learnmeabitcoin.com/technical/hd-wallets) | 15 |
| [Mnemonic Code Converter](https://iancoleman.io/bip39/) | x |
| [Coin Selection](https://btctranscripts.com/scalingbitcoin/tokyo-2018/edgedevplusplus/coin-selection/) | 25 |
| [An Introduction to Bitcoin Core Fee Estimation](https://medium.com/bitcoin-tech-talk/an-introduction-to-bitcoin-core-fee-estimation-27920880ad0) | 15 |
| [Fee Bumping and RBF](https://github.com/bitcoinops/scaling-book/blob/add_rbf/1.fee_bumping/fee_bumping.md) | 25 |
| \(_optional_\) [PSBT with Andrew Chow](https://btctranscripts.com/sf-bitcoin-meetup/2019-03-15-partially-signed-bitcoin-transactions) | 25 |
| \(_optional_\) Native Descriptor Wallets - [gist](https://gist.github.com/achow101/94d889715afd49181f8efdca1f9faa25) or [presentation](https://btctranscripts.com/advancing-bitcoin/2020/2020-02-06-andrew-chow-descriptor-wallets/) | 15 or 20 |
| [Schnorr Signatures & The Inevitability of Privacy in Bitcoin](https://medium.com/digitalassetresearch/schnorr-signatures-the-inevitability-of-privacy-in-bitcoin-b2f45a1f7287) | 20 |
| \(_optional_\) [MuSig-DN: Schnorr Multisignatures with Verifiably Deterministic Nonces](https://medium.com/blockstream/musig-dn-schnorr-multisignatures-with-verifiably-deterministic-nonces-27424b5df9d6) | 15 |
| [Taproot Explained \(_video_\)](https://www.youtube.com/watch?v=d82-MPwpiYs) | 15 |
| [Overview of the Taproot & Tapscript BIPs](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips) | 25 |
| [Scriptless Scripts](https://bitcoinmagazine.com/articles/scriptless-scripts-how-bitcoin-can-support-smart-contracts-without-smart-contracts) | 15 |
| \(_optional_\) [Optech Series: Preparing for Taproot](https://bitcoinops.org/en/preparing-for-taproot/) | 70 |
| \(_optional_\) [On Building Consensus and Speedy Trial](http://r6.ca/blog/20210615T191422Z.html) | 25 |

## Optional Practical Exercise

* [Taproot, sighash, timelock transaction exercises (chapters 3-5)](https://github.com/chaincodelabs/bitcoin-tx-tutorial)
* [Taproot workshop by Bitcoin Optech Group](https://bitcoinops.org/en/schorr-taproot-workshop/) \(3+ hours\)

## Discussion Questions

### SCRIPT

1. John Newbery talks about [verification vs. computation](https://youtu.be/np-SCwkqVy4?t=934), and he bring it up as a big reason why he thinks bitcoin can scale but is skeptical about ethereum. Is there a qualitative difference between verification and computation? And is it the fact that ethereum is capable of performing arbitrary computation that makes the whole thing difficult to scale, or is it that specifically smart contracts that require arbitrary computation won’t be able to scale \(as in those contracts would be very expensive to run\)?

### Output Descriptors

1. What is the benefit of using output descriptors?
2. How does miniscript interact with descriptors?

### HD Wallets

1. What is the difference between child and hardened child addresses?
2. Why is the internal chain not visible outside of the wallet if it uses public derivation?

### Coin Selection

1. Is coin age ever a consideration for coin selection?
2. Coin selection can expose a wallet by observing how the wallet selects its inputs, are there any efforts to standardize coin selection into a library of sorts so there's a standard?

### Fee Bumping and RBF

1. Is there way to ensure that a transaction will be processed? What tools are available to ensure a stuck transaction \(due to low fees\) gets processed?
2. While inconvenient, could a stuck transaction lead to a loss of funds?

### Schnorr signatures

1. How are schnorr signatures reducing a transaction's data footprint?
2. How can validation of schnorr signatures be sped up?
3. Why may schnorr signatures incentivize multi-spender transactions?
4. What makes Schnorr signatures shorter?
5. Why do schnorr signatures need a nonce?
6. What is the risk of nonce-generation on a limited-entropy device like a hardware wallet? How can that risk be overcome with deterministic nonce generation?

### Taproot

1. What makes Pay to Taproot more private than previous output formats?
2. What are the difficulties and benefits of switching to Pay to Taproot addresses?
3. Why does tapscript not support OP\_CHECKMULTISIG?
4. What is the purpose of TaggedHashes?

### \(_optional_\) The softfork bundle

1. Would it be possible to implement Taproot without schnorr signatures or schnorr outputs without Taproot?
2. How did the Bitcoin network settle on using Speedy Trial to activate Taproot?

### \(_optional_\) Native segwit output and bech32 addresses

1. What's the difference between "native segwit" and "bech32\(m\)"?
2. Should wallets allow sending to bech32m addresses?

