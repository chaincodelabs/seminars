# P2P

*Note that this section depends on reviewing the network propagation resources of the mining and network propagation study group. If you are doing these out of order, please take a look at that section first.*

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
Attacking P2P of Bitcoin Core w/ Amiti Uttarwar ([video (until min 41)](https://youtu.be/H-wH6mY9pZo?t=257) or [transcript](hhttps://btctranscripts.com/la-bitdevs/2020-04-16-amiti-uttarwar-attacking-bitcoin-core/) | 35 min | p2p attacks |
[The Bitcoin p2p Network with John Newbery](https://btctranscripts.com/scalingbitcoin/stanford-2017/edgeplusplus/p2p-john-newbery/) | 51 min | P2P, video |
[The Bitcoin Network in Mastering Bitcoin (start at Network Discovery section)](https://github.com/bitcoinbook/bitcoinbook/blob/b5a7b5df3eddb332311ed97af09b678257ce62ca/ch08.asciidoc#network-discovery) | 15 min | P2P |
[Network partition resistance](https://gist.github.com/sdaftuar/c2a3320c751efb078a7c1fd834036cb0) | 15 min | P2P |
[Eclipse Attacks on Bitcoin’s Peer-to-Peer Network](https://eprint.iacr.org/2015/263.pdf) | 60 min | eclipse attacks, P2P |
[Network partitioning & network level privacy attacks](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-12-ethan-heilman-network-partitioning-attacks/) | 40 min | eclipse attacks, privacy, P2P |
[Researching P2P privacy attacks](https://youtu.be/qKNEUfnYue0) | 90 min | P2P, privacy, video, _optional_ |

## Discussion Questions

### Attacking P2P

1. Given the attack surface in P2P, is running a full node worth it?
1. How many honest nodes do you need to be connected to be sure you are connected to the right network/blockchain?

### P2P Connections

1. What is the reasoning behind the max inbound and max outbound defaults? For which type of user would they be considered ideal, and when might they be optimized?
1. What is the rationale behind the "new"/"tried" table design? Were there any prior inspirations within the field of distributed computing?
1. How does a fixed set of 4 outbound peers get chosen? In what circumstances would you evict or change them?
1. What are feeler connections, and when are they used?

### Eclipse Attacks on Bitcoin’s Peer-to-Peer Network

1. What can an attacker do if they are able to eclipse a mining pool?
1. What is the difficulty of successfully achieving an eclipse attack? What resources and skills would be required to achieve such an attack?

### Transaction Trivia

1. Why must transaction unlocking scripts only push numbers to be relayed?
1. What output scripts are 'IsStandard'?
1. Why must transactions be no less than 82 bytes to be relayed?
1. Why is the blockheight now encoded in the coinbase transaction?

### [OPTIONAL] Researching P2P privacy attacks

1. How does "diffusion" message spreading work and why is it ineffective against de-anonymization?
