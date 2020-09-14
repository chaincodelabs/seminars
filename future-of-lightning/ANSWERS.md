# Some Responses to the Discussion Questions

### eltoo
Q: why do we need sighash_noinput for eltoo?  
A: Instead of having to publish the entire sequence of update transactions all the way to your most recent settlement transaction, SIGHASH_NOINPUT allows you to skip over all update transactions until the one you need.

### Submarine swaps
Q: Can an adversary make a swap and wait for the last minute before the lock expires and then reveal the secret on one chain and tries to use the signature on the other? If the blocks there are pretty fast he might be able to get off with the money from both chains.  
A: No, usually there will be sufficiently large offset between expirations. Of course these are negotiated between the participants but generally that should be the case.
