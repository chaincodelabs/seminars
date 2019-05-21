# SegWit

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
| [An Introduction to SegWit](https://segwit.org/understanding-segregated-witness-905cc712c692) | 5 min | primer                  |
| [Transaction Malleability Primer](https://bitcointechtalk.com/transaction-malleability-explained-b7e240236fc7) | 5 min | tx malleability, primer |
| [SegWit in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/develop/ch07.asciidoc#segregated-witness) | 25 min |
| [SegWit's Impact on Scalability](https://diyhpl.us/wiki/transcripts/scalingbitcoin/hong-kong/segregated-witness-and-its-impact-on-scalability/) | 30 min video | 2015, scale |
| [SegWit Revisited](https://www.youtube.com/watch?v=AjBpIkfB-ac) | 7 min | technical                                            |
| [SegWit with Jimmy Song](https://www.youtube.com/watch?v=Txfy2mFe16A) | 27 min | technical                                            |
| [SegWit Benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) | 12 min | technical                                  |
| [SegWit Costs](https://bitcoincore.org/en/2016/10/28/segwit-costs/) | 20 min | technical                                        |
| [Transaction Malleability](https://www.youtube.com/watch?v=jyDE-aFqJTs) | first 21 min of video | malleability, technical, 2014 |
| [2015 Malleability Attack](https://bitcoinmagazine.com/articles/the-who-what-why-and-how-of-the-ongoing-transaction-malleability-attack-1444253640/) | 10 min | malleability, attack vectors |
| [The Long Road to SegWit](https://bitcoinmagazine.com/articles/long-road-segwit-how-bitcoins-biggest-protocol-upgrade-became-reality/) | 20 min | history |
| [SegWit Wallet Development](https://bitcoincore.org/en/segwit_wallet_dev/) | 10 min | wallet, technical                  |
| [Bech32](https://diyhpl.us/wiki/transcripts/sf-bitcoin-meetup/2017-03-29-new-address-type-for-segwit-addresses/) | 35 min video | bech32 |
| [Code Walkthrough](https://docs.google.com/document/d/1qn9SCQj2YQauE83FjglODUZJTQaz9WxrbaTtkP367cA/edit) | 20 min | code                  |

## Discussion Questions

1. How is DER malleable? How is ECDSA malleable?
2. In this [video](https://youtu.be/AjBpIkfB-ac?t=149) James describes how the input script operation can be malleated without affecting validity. Can you speak more to how this can be taken advantage of? You mentioned it wasn't easy to correct, but are there any proposals to fix?
3. Why do layering protocols require tx malleability to be fixed?
2. How should one understand anyone-can-spend outputs? Do nodes with and without the SegWit upgrade behave differently while validating enforcing? How?
3. How do the SegWit script versions conceptually differ from the versions on transactions? Why couldn't the transaction versions be used to support newer functionality without hard forks?
4. Where are the locking script operations in P2WPKH/P2WSH?
5. How can new script versions remain backwards compatible?
6. What is weight/virtual bytes?
7. What rationale was used to decide on the 4 MB SegWit block weight (3 x old_tx_bytes + segwit_tx_bytes), instead of say a 2 MB block weight (old_tx_bytes + segwit_tx_bytes)?
8. How is witness data committed to the block?
9. What is the quadratic sighash problem prior to Segwit? How does [BIP 143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) solve this?
10. What would be the additional steps to include the fraud proofs described at the bottom of [this doc](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) and by [Sipa in 2015](https://diyhpl.us/wiki/transcripts/scalingbitcoin/hong-kong/segregated-witness-and-its-impact-on-scalability/) via a softfork?
11. How do users know whether miners support SegWit prior to activation?
12. How does a (virtual block increase) affect IBD cost over time?
