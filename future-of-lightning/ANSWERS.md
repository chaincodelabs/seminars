# Some Responses to the Discussion Questions

### eltoo
Q: Why do we need SIGHASH_NOINPUT for eltoo?  
A: Instead of having to publish the entire sequence of update transactions all the way to your most recent settlement transaction, SIGHASH_NOINPUT allows you to skip over all update transactions until the one you need.

### Submarine swaps
Q: Can an adversary make a swap and then wait until a moment before the lock expiry to reveal the secret on one chain while using the signature on the other? If the blocks are fast, could an attacker be able to steal the money from both chains?  
A: No, usually there will be sufficiently large offset between expirations. Of course these are negotiated between the participants but generally that should be the case.
