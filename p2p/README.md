# P2P

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Bitcoin Peer-to-Peer Network with John Newbery](https://youtu.be/eVerdR2hOMw) | 51 min | P2P, video |
[Mining and Consensus in Mastering Bitcoin - through SPV nodes section](https://github.com/bitcoinbook/bitcoinbook/blob/f8b883dcd4e3d1b9adf40fed59b7e898fbd9241f/ch08.asciidoc#network-discovery) | 15 min | P2P |
[Compact Blocks](https://bitcoincore.org/en/2016/06/07/compact-blocks-faq/) | 7 min | compact blocks |
[Network partition resistance](https://gist.github.com/sdaftuar/c2a3320c751efb078a7c1fd834036cb0) | 15 min | P2P |
[Deanonymization in the Bitcoin P2P Network](https://papers.nips.cc/paper/6735-deanonymization-in-the-bitcoin-P2P-network.pdf) | 15 min | P2P, privacy |
[Eclipse Attacks on Bitcoin’s Peer-to-Peer Network ](https://eprint.iacr.org/2015/263.pdf) | 60 min | eclipse Attacks, P2P |
[Eclipse Attacks Video](https://www.usenix.org/node/190891) | 27 min | eclipse Attacks, P2P, video |
[Dandelion: Redesigning the Bitcoin Network for Anonymity](https://arxiv.org/pdf/1701.04439.pdf) | 20 min | P2P, privacy |


## Discussion Questions

### P2P Connections
1. What is reasoning behind the max inbound and max outbound defaults? For which type of user would they be considered ideal and when might they be optimized?
2. What is the rationale behind the "new"/"tried" table design? Were there any prior inspirations within the field of distributed computing?
3. How does a fixed set of 4 outbound peers get chosen? In what circumstances would you evict/change them?

### De-anonymization
4. How does "diffusion" message spreading work? and why is it ineffective against de-anonymization?

### Dandelion
5. How are routes chosen (in the stem phase)? What happens if a malicious (or faulty) node doesn't propagate your transaction in the stem phase?
6. When a transaction is going to bloom depends on a weighted coin toss at each hop- how is that weight determined? Could an adversarial node overwrite that weight to ensure bloom?
7. Dandelion++ is meant to address the assumptions from the original Dandelion paper. How is that achieved?
Assumptions:
  a) All nodes obey the protocol
  b) Each node generates precisely one transaction
  c) All Bitcoin nodes run Dandelion

### SPV filters
8. Bloom filters vs BIP157/BIP158 Golomb Coded Set, how do you build them? Properties? Scope?

### P2P Stack
9. Alternative P2P stack with different design tradeoffs (likely based on PIR) ? (need to dig in bitcoin-wizards logs)

### P2P tx relay and UTXO
10. Are confirmed and unconfirmed outputs in the same UTXO cache? For validation and lookup during TX relay...
11. How the default values affect the throughput of the whole network? Did anyone ever tried to analyze how much data the bitcoin P2P network can handle both in bandwidth and latency?
