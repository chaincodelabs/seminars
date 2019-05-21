# Wallets and PSBT

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Wallet Types](http://bcoin.io/guides/wallets.html) | 15 min | wallet types |
[HD Wallets](https://medium.com/bitcraft/hd-wallets-explained-from-high-level-to-nuts-and-bolts-9a41545f5b0) | 5 min | HD wallets |
[BIP 32 - Hierarchical Deterministic Wallets](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki) | 15 min | HD wallets |
[Hardware Wallets with Bitcoin Core](https://vimeo.com/316634495) | 23 min | hardware wallets |
[Output Descriptors](https://gist.github.com/sipa/e3d23d498c430bb601c5bca83523fa82) | 5 min | output descriptors |
[Coin Selection](https://bitcoinedge.org/tutorial/EN:wallets-coin-selection) | 20 min | coin selection |
[Fees](https://medium.com/@jimmysong/the-fee-market-explained-76b294947b42) | 5 min | fees |
[Transaction Replacement](https://en.bitcoin.it/wiki/Transaction_replacement)  | 5 min | transaction replacement, fees |
[Fee Bumping and RBF](https://github.com/bitcoinops/scaling-book/blob/add_rbf/1.fee_bumping/fee_bumping.md) | 10 min | fee bumping, RBF |
[PSBT presented by @achow101](https://www.youtube.com/watch?v=H6xZSRDXUiU) | 30 min | PSBT, video |
[PSBT - Howto for Bitcoin Core](https://github.com/bitcoin/bitcoin/blob/master/doc/psbt.md) | 5 min | PSBT |


## Discussion Questions

### Output Descriptors
1. Are there any use cases for p2sh-wsh-p2pkh descriptors?
2. What's about miniscript? Interactions with descriptors?

### HD Wallets
3. What is the difference between child and hardened child addresses?
4. Why is the internal chain not visible outside of the wallet if it uses public derivation?

### Coin Selection
5. Is coin age ever a consideration for coin selection?
6. Coin selection can expose a wallet by observing how the wallet selects its inputs, are there any efforts to standardize coin selection into a library of sorts so there's a standard?
