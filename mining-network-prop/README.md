# Mining and Network Block Propagation

## Reading

| Content                                                            | Time       | Tags                    |
|--------------------------------------------------------------------|------------|-------------------------|
[Mining and Consensus in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/f8b883dcd4e3d1b9adf40fed59b7e898fbd9241f/ch10.asciidoc) | 75 min | mining, pools, primer, *optional* |
[Advances in Block Propagation with Greg Maxwell](https://diyhpl.us/wiki/transcripts/gmaxwell-2017-11-27-advances-in-block-propagation/) | 60 min | block propagation |
[Compact Blocks](https://bitcoincore.org/en/2016/06/07/compact-blocks-faq/) | 10 min | compact blocks |
[Relay Networks and FIBRE](https://bluematt.bitcoin.ninja/2016/07/07/relay-networks/) | 10 min | relay network, FIBRE |
[Mining: No Good, The Bad, and The Ugly](https://www.youtube.com/watch?v=k_z-FBAil6k) | 15 min | mining, stratum, video |
[Why Bitcoin Mining Pools Aren't Incentivized to Broadcast Blocks Quickly](https://bitcoinmagazine.com/articles/why-bitcoin-mining-pools-aren-t-incentivized-to-broadcast-blocks-quickly-1475249510/) | 10 min | spy mining |
[Majority is not Enough: Bitcoin Mining is Vulnerable](https://www.cs.cornell.edu/~ie53/publications/btcProcFC.pdf) | 30 min | selfish mining |
[Demystifying The Selfish Mining Bet](https://eklitzke.org/demystifying-the-selfish-mining-bet) | 10 min | selfish mining |
[Analysis of Bitcoin Pooled Mining Reward Systems](https://sites.cs.ucsb.edu/~rich/class/cs293b-cloud/papers/bitcoin-pool.pdf) (Intro, Pay-per-share, Pay-per-last-N-shares, Attack Vectors sections) | 30 min | mining pools |
[The problem with ASIC Boost](http://www.mit.edu/~jlrubin//public/pdfs/Asicboost.pdf) | 15 min | asic boost |
[Compact Blocks/FIBRE background](https://podcast.chaincode.com/2020/03/12/matt-corallo-6.html) | 32 min | FIBRE, history, podcast, *optional* |

## Discussion Questions

1. How can changes to Bitcoins p2p protocol affect mining? (Advances in Block Propagation)
1. How does the FIBRE network work and what were the motivations to iterate on the original Relay Network? (Relay Networks and FIBRE)
1. How do pools give work assignments to client miners? Do all miners search the same block candidates?
1. What are 'shares' and how do they help facilitate pooled mining?
1. Consider the following scenario: Segwit2x didn’t happen (or miners didn’t throw in support for it) and UASF (BIP148) ended up causing a chain split on August 1st, 2017, with minority mining support (e.g. ~10-20%). What would likely happen as a result?
1. How far back into the past can the timestamp in blocks be? Is this validated? How can this be attacked?
1. What is the 'Selfish Mining' attack? How does it work? Is it a real threat? Why or why not? (Majority is not Enough)
1. What is a BGP Hijack attack? What prevents it? (Mining: No Good, The Bad, and The Ugly)
1. What is a block withholding attack? Why isn't it used more often? What is the defense?
1. What is a share withholding attack? Why isn't it used more often? What is the defense?
1. How do P2Pools work? Advantages and disadvantages? (Mining and Consensus in Mastering Bitcoin)
1. Why not encrypt all communications with pool operators?
1. Why would some miners use parts of the version field as a nonce? What effect did this have on nodes? (Mining and Consensus in Mastering Bitcoin)
1. What is the difference between overt and covert ASIC Boost? (The problem with ASIC Boost)
1. Have we seen the difficulty retarget algorithm be manipulated in other projects? Is this a threat to Bitcoin?
