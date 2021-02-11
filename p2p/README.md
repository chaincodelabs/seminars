# P2P

*Note that this section depends on reviewing the network propagation resources of the mining and network propagation study group. If you are doing these out of order, please take a look at that section first.*

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
Attacking p2p of Bitcoin Core w/ Amiti Uttarwar ([video (until min 41)](https://youtu.be/H-wH6mY9pZo?t=257) or [transcript](https://diyhpl.us/wiki/transcripts/la-bitdevs/2020-04-16-amiti-uttarwar-attacking-bitcoin-core/)) | 35 min | p2p attacks |
[The Bitcoin p2p Network with John Newbery](https://diyhpl.us/wiki/transcripts/scalingbitcoin/stanford-2017/edgeplusplus/p2p-john-newbery/) | 51 min | P2P, video |
[The Bitcoin Network in Mastering Bitcoin (start at Network Discovery section)](https://github.com/bitcoinbook/bitcoinbook/blob/b5a7b5df3eddb332311ed97af09b678257ce62ca/ch08.asciidoc#network-discovery) | 15 min | P2P |
[Network partition resistance](https://gist.github.com/sdaftuar/c2a3320c751efb078a7c1fd834036cb0) | 15 min | P2P |
[Deanonymization in the Bitcoin P2P Network](https://papers.nips.cc/paper/6735-deanonymization-in-the-bitcoin-p2p-network.pdf) | 15 min | P2P, privacy |
[Eclipse Attacks on Bitcoin’s Peer-to-Peer Network](https://eprint.iacr.org/2015/263.pdf) | 60 min | eclipse attacks, P2P |
[Network partitioning & network level privacy attacks](http://diyhpl.us/wiki/transcripts/chaincode-labs/2019-06-12-ethan-heilman-network-partitioning-attacks/) | 40 min | eclipse attacks, privacy, P2P |
[Researching P2P privacy attacks](https://youtu.be/qKNEUfnYue0) | 90 min | P2P, privacy, video, _optional_ |

## Discussion Questions

### P2P Connections

1. What is the reasoning behind the max inbound and max outbound defaults? For which type of user would they be considered ideal, and when might they be optimized?
1. What is the rationale behind the "new"/"tried" table design? Were there any prior inspirations within the field of distributed computing?
1. How does a fixed set of 4 outbound peers get chosen? In what circumstances would you evict or change them?
1. What are feeler connections, and when are they used?

### De-anonymization

1. How does "diffusion" message spreading work, and why is it ineffective against de-anonymization?

### Transaction Trivia

1. Why must transaction unlocking scripts only push numbers to be relayed?
1. What output scripts are 'IsStandard'?
1. Why must transactions be no less than 82 bytes to be relayed?
1. Why is the blockheight now encoded in the coinbase transaction?
