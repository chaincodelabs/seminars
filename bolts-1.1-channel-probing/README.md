# Channel Probing, Submarine Swaps/Loops, BOLTs 1.1

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[On the Difficulty of Hiding the Balance of Lightning Network Channels](https://eprint.iacr.org/2019/328.pdf) | Start at section 3, 30 min | privacy, lightning |
[Submarine Swaps](http://diyhpl.us/wiki/transcripts/magicalcryptoconference/2019/submarine-swaps/) | 5 min | submarine swaps |
[Loops](https://blog.lightning.engineering/posts/2019/03/20/loop.html) | 5 min | loops, liquidity |
[Submarine swaps/ Loops](https://youtu.be/qixhNBIHDyE) | 42 min | loops, submarine swaps, video |
[Lightning Specification 1.1 Proposal States](https://github.com/lightningnetwork/lightning-rfc/wiki/Lightning-Specification-1.1-Proposal-States) | 10 min | BOLTs, future |
[Breaking Down the Bitcoin Lightning Network: eltoo](https://medium.com/@brandonarvanaghi/breaking-down-the-bitcoin-lightning-network-eltoo-c48554f5ae02) | 11 min | eltoo |
[Eltoo and the Far Future](https://diyhpl.us/wiki/transcripts/chaincode-labs/2019-09-18-christian-decker-eltoo/) | 30 min | eltoo |
[Splicing](https://youtu.be/ZzSveBMtUGI) | 22 min | BOLTs, video |
[Multi-party channels/Channel factories](https://youtu.be/PUDWGH_MvmQ) | 13 min | BOLTs, video |
[Rendezvous Routing](https://youtu.be/Ms2WwRzBdkM) | 8 min | BOLTs, video |
[Dual funded channels](https://youtu.be/5wQUMtgsnPs) | 35 min | BOLTs, video |

## Discussion Questions

### Balance Probing Attack
1. 	It sounds like randomly denying a percentage of payment requests would be an efective countermeasure. Outside of the potential loss of routing fees, are there any other downsides? IMO, this sounds like a great trade-off relative to the privacy leakage.
2. Another countermeasure was to remove error messages when a route fails. Besides having less clarity as to why a path failed when trying to find a route for a payment, are there any other reasons to include these error messages? When trying to find a path, if one of the links did not have enough capacity and you got a generic error message, you'd still keep trying enough paths and eventually get the payment through. If the problem was something else, like in the attack the destination node doesn't have the preimage for the HTLC, then after enough fails the sender would realize the problem is likely in the destination node. Is there a good use case for keeping the path error messages?

### Submarine swaps
3. Can an adversary make a swap and wait for the last minute before the lock expires and then reveal the secret on one chain and tries to use the signature on the other? If the blocks there are pretty fast he might be able to get off with the money from both chains.


### Rendezvous Mechanism

4. Can someone breakdown Rendezvous into more basic language?
5. Would it make sense to chain multiple RV (meeting point)?
6. How does rendezvous protect against the following scenario: The sender controls the selected rendezvous node. How this could happen: The sender of the payment wants to know the location of the receiver, the receiver selects a rendezvous node for each invoice randomly. The sender can spin up a bunch of rendezvous enabled nodes on the network and request invoices from the receiver until one of her nodes are selected as the rendezvous node.
