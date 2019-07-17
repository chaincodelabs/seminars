# Channel Probing, BOLTs 1.1, Submarine Swaps/Loops, HTLC-DASH

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[On the Difficulty of Hiding the Balance of Lightning Network Channels](https://eprint.iacr.org/2019/328.pdf) | Start at section 3, 30 min | privacy, lightning |
[Lightning Specification 1.1 Proposal States](https://github.com/lightningnetwork/lightning-rfc/wiki/Lightning-Specification-1.1-Proposal-States) | 10 min | BOLTs, future |
[Submarine Swaps](http://diyhpl.us/wiki/transcripts/magicalcryptoconference/2019/submarine-swaps/) | 5 min | submarine swaps |
[Loops](https://blog.lightning.engineering/posts/2019/03/20/loop.html) | 5 min | loops, liquidity |
[Rendezvous Mechanism on Top of Sphinx](https://github.com/lightningnetwork/lightning-rfc/wiki/Rendez-vous-mechanism-on-top-of-Sphinx) | 5 min | routing |
[DASH wikipedia Article](https://en.m.wikipedia.org/wiki/Dynamic_Adaptive_Streaming_over_HTTP) | 10 min | DASH |
[HTLC-DASH](https://www.bitcoinlightning.com/laolu-lightning-network-powered-video-platform/) | 5 min | HTLC-DASH |
[HTLC-DASH Presentation by Laolu](https://docs.google.com/presentation/d/16BK53bnfRVu_iHJKw2f82DRg6kk8061gxiJeKTCciKY/edit#slide=id.g2005d26133_0_17) | 15 min, optional | HTLC-DASH |


## Discussion Questions

### Balance Probing Attack
1. 	It sounds like randomly denying a percentage of payment requests would be an efective countermeasure. Outside of the potential loss of routing fees, are there any other downsides? IMO, this sounds like a great trade-off relative to the privacy leakage.
2. Another countermeasure was to remove error messages when a route fails. Besides having less clarity as to why a path failed when trying to find a route for a payment, are there any other reasons to include these error messages? When trying to find a path, if one of the links did not have enough capacity and you got a generic error message, you'd still keep trying enough paths and eventually get the payment through. If the problem was something else, like in the attack the destination node doesn't have the preimage for the HTLC, then after enough fails the sender would realize the problem is likely in the destination node. Is there a good use case for keeping the path error messages?

### Rendezvous Mechanism

3. Can someone breakdown Rendez vous into more basic language?
4. Would it make sense to chain multiple RV (meeting point)?
5. How does rendezvous protect against the following scenario: The sender controls the selected rendezvous node. How this could happen: The sender of the payment wants to know the location of the receiver, the receiver selects a rendezvous node for each invoice randomly. The sender can spin up a bunch of rendezvous enabled nodes on the network and request invoices from the receiver until one of her nodes are selected as the rendezvous node.

### HTLC-DASH
6. It's not clear how the "Payment hash is segment content hash: Claim of payment reveals segment" works to achieve an atomic 'fair exchange' of payment for video segments. If the requests are for a hash of a segment, and HTLCs are spendable with the pre-image of the hash, then what incentive does the payment receiver have to actually send the segment? If they have the content they can spend the payment, but no way to force them to transmit it.

### Submarine swaps
7. Can an adversary make a swap and wait for the last minute before the lock expires and then reveal the secret on one chain and tries to use the signature on the other? If the blocks there are pretty fast he might be able to get off with the money from both chains.
