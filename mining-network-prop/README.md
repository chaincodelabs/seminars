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
[Mining pools](https://en.wikipedia.org/wiki/Mining_pool) | 15 min | mining pools |
[Overview of the covert AsicBoost allegation](https://blog.bitmex.com/an-overview-of-the-covert-asicboost-allegation-2/) | 15 min | asic boost |

## Discussion Questions

### Mining and Consensus

1. Why would some miners use parts of the version field as a nonce? What effect did this have on nodes?
1. How do P2Pools work? Advantages and disadvantages? Why aren't there any mainstream P2Pools today in the market?
1. How far back into the past can the timestamp in blocks be? Is this validated? How can this be attacked?
1. Have we seen the difficulty retarget algorithm be manipulated in other projects? Is this a threat to Bitcoin?
1. In your opinion, is it a good or bad thing that specialized hardware is now needed to mine bitcoin rather than letting individual users participate in that part of the ecosystem?
1. Consider the following scenario: Segwit2x didn’t happen (or miners didn’t throw in support for it) and UASF (BIP148) ended up causing a chain split on August 1st, 2017, with minority mining support (e.g. ~10-20%). What would likely happen as a result?

### Advances in Block Propagation

1. How can changes to Bitcoins p2p protocol affect mining?
1. How is a high block-orphaning rate the best indicator that block propagation times are too high?
1. Alternatively, while a low block-orphaning rate can be an indicator that block propagation times are good, it could also be an indicator of something more problematic. What could be a bad reason for there to be very few orphans?
1. Greg Maxwell mentioned that miners are hesitant to connect with one another directly, even though it would speed up block propagation. Why?

### Compact Blocks

1. How could we speed up block propagation in the network like FIBRE does, but without the drawback of having to trust others?
1. Compact block relay is a good way to reduce the amount of bandwidth to propagate new blocks to full nodes, but is it the fastest method for a synced node given peers may need to request missing transactions?

### Relay Networks and FIBRE

1. How does the FIBRE network work and what were the motivations to iterate on the original Relay Network?

### Mining: No Good, The Bad, and The Ugly

1. What is a BGP Hijack attack? What prevents it? (Mining: No Good, The Bad, and The Ugly)
1. Why not encrypt all communications with pool operators?

### Majority is not Enough

1. What is the 'Selfish Mining' attack? How does it work? Is it a real threat?
1. Is it possible to identify and ignore a Selfish Miner's chain? Must we follow the most-work chain even if we identify that it came from a selfish miner?

### Mining pools

1. How do pools give work assignments to client miners? Do all miners search the same block candidates?
1. What are 'shares' and how do they help facilitate pooled mining?

### Overview of the covert AsicBoost allegation

1. What is the difference between overt and covert ASIC Boost?
