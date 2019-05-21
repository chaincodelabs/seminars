# Mining and Network Propagation

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Mining and Consensus in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/f8b883dcd4e3d1b9adf40fed59b7e898fbd9241f/ch10.asciidoc) | 90 min | mining, pools |
[Majority is not Enough: Bitcoin Mining is Vulnerable](https://www.cs.cornell.edu/~ie53/publications/btcProcFC.pdf) | 30 min | mining |
[Stratum Spec](https://slushpool.com/help/topic/stratum-protocol/) | 15 min | mining pools |
[The problem with Asic Boost](http://www.mit.edu/~jlrubin//public/pdfs/Asicboost.pdf) | 15 min | asic boost |
[Optimal pool abuse strategy](http://bitcoin.atspace.com/poolcheating.pdf) | 10 min | mining pools |
[Analysis of Bitcoin Pooled Mining Reward Systems](https://sites.cs.ucsb.edu/~rich/class/cs293b-cloud/papers/bitcoin-pool.pdf) (Intro, Pay-per-share, Pay-per-last-N-shares sections) | 30 min | mining pools |
[p2p pools](https://en.bitcoin.it/wiki/P2Pool) | 20 min | mining pools |
[The Original Relay Network](https://www.youtube.com/watch?v=QpK6k0yRDWI) | 30 min video | relay network |
[Why Bitcoin Mining Pools Aren’t Incentivized to Broadcast Blocks Quickly](https://bitcoinmagazine.com/articles/why-bitcoin-mining-pools-aren-t-incentivized-to-broadcast-blocks-quickly-1475249510/) | 10 min | spy mining |
[BIP 152](https://github.com/bitcoin/bips/blob/master/bip-0152.mediawiki) - #motivation, #spec for v1, #justification sections | 10 min | compact blocks |
[Relay Networks and FIBRE](https://bluematt.bitcoin.ninja/2016/07/07/relay-networks/) | 10 min | relay network, FIBRE |
[FIBRE website](http://bitcoinfibre.org) | 15 min | FIBRE |

## Discussion Questions

1. Why is the blockheight now encoded in the coinbase transaction?
2. What is the difference between overt and covert ASIC Boost?
3. Why would some miners use parts of the version field as a nonce? What effect did this have on nodes?
4. How can changes to Bitcoins p2p protocol effect mining?
5. Consider the following scenario: Segwit2x didn’t happen (or miners didn’t throw in support for it) and UASF (BIP148) ended up causing a chain split on August 1st, 2017, with minority mining support (e.g. ~10-20%). What would likely happen as a result?
6. How far back into the past can the timestamp in blocks be? Is this validated?
7. Why must transaction unlocking scripts only push numbers to be relayed? What output scripts are 'IsStandard'?
8. Why must transactions be > 82 bytes to be relayed?
9. How does the FIBRE network work and what were the motivations to iterate on the original Relay Network?
10. What is a BGP Hijack attack? What prevents it?
11. What is the 'Selfish Miner' attack? How does it work? Is it a real threat? Why or why not?
12. What is a share withholding attack? Why isn't it used more often? What is the defense?
13. How is the BetterHash mining protocol different then the current Stratum protocol?
14. How is the P2Pool work? Advantages and disadvantages?
15. Why not encrypt all communications with pool operators?
16. What are 'Weak Blocks' and why are they used in pooled mining?
17. Does pool parallelize work among client miner to avoid them starting on the same range of search space and so increase chance of finding a block?
