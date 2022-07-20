# P2P

_Note that this section depends on reviewing the network propagation resources of the mining and network propagation seminar. If you are doing these out of order, please take a look at that section first._

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Map of the Bitcoin Network](https://medium.com/@gloriazhao/map-of-the-bitcoin-network-c6f2619a76f3) | 20 |
| Attacking p2p of Bitcoin Core w/ Amiti Uttarwar \([video \(until min 41\)](https://youtu.be/H-wH6mY9pZo?t=257) or [transcript](https://btctranscripts.com/la-bitdevs/2020-04-16-amiti-uttarwar-attacking-bitcoin-core/)\) | 35 |
| [The Bitcoin p2p Network with John Newbery](https://btctranscripts.com/scalingbitcoin/stanford-2017/edgeplusplus/p2p-john-newbery/) | 50 |
| [The Bitcoin Network in Mastering Bitcoin \(start at Network Discovery section\)](https://github.com/bitcoinbook/bitcoinbook/blob/b5a7b5df3eddb332311ed97af09b678257ce62ca/ch08.asciidoc#network-discovery) | 15 |
| [Network partition resistance](https://gist.github.com/sdaftuar/c2a3320c751efb078a7c1fd834036cb0) | 15 |
| [Eclipse Attacks on Bitcoin’s Peer-to-Peer Network](https://eprint.iacr.org/2015/263.pdf) | 60 |
| [Network partitioning & network level privacy attacks](http://btctranscripts.com/chaincode-labs/2019-06-12-ethan-heilman-network-partitioning-attacks/) | 40 |
| \(_optional_\) [Researching P2P privacy attacks](https://youtu.be/qKNEUfnYue0) \(video\) | 90 |

## Optional Practical Exercise

- [Will Clark](https://github.com/willcl-ark) has an updated fork of [tinybitcoinpeer](https://github.com/willcl-ark/tinybitcoinpeer), a 200 line python program that allows you to explore the Bitcoin p2p network.

## Discussion Questions

### Attacking P2P

1. Given the attack surface in P2P, is running a full node worth it?
2. How many honest nodes do you need to be connected to be sure you are connected to the right network/blockchain?
3. Does it make sense to have separate networks which are more resistant against p2p attacks, and regular nodes will keep at least one connection to them if they choose so?

### P2P Connections

1. What is the reasoning behind the max inbound and max outbound defaults? For which type of user would they be considered ideal, and when might they be optimized?
2. What is the rationale behind the "new"/"tried" table design? Were there any prior inspirations within the field of distributed computing?
3. How are anchor connections chosen? In what circumstances would you evict or change them?
4. What are feeler connections, and when are they used?
5. How many honest nodes does a node need to connect to ensure it is connected to the right network/blockchain?

### Eclipse Attacks on Bitcoin’s Peer-to-Peer Network

1. What can an attacker do if they are able to eclipse a mining pool?
2. What is the difficulty of successfully achieving an eclipse attack? What resources and skills would be required to achieve such an attack?

### Transaction Trivia

1. Why must transaction unlocking scripts only push numbers to be relayed?
2. What output scripts are 'IsStandard'?
3. Why must transactions be no less than 82 bytes to be relayed?
4. Why is the blockheight now encoded in the coinbase transaction?

### \[OPTIONAL\] Researching P2P privacy attacks

1. How does "diffusion" message spreading work and why is it ineffective against de-anonymization?
