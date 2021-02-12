# Some Responses to the Discussion Questions

Q: Given the fact that Lightning is punishment-based and requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds?  
A: (a) Yes. If you lose your channel state and your counterpart respond to you with an older `per_commitment_secret` in a `channel_reestablish` message, you're likely going to use a revoked `per_commitment_point` for your next commitment transaction and then the malicious counterparty forces you to unilateral close the channel. At that point, the counterparty already the secret to build justice transaction on. (b) If you use a watchtower that stores your commitment transactions, but it is not trustworthy.

### HTLCs

Q: Is it correct to say that under "normal" working conditions, if all payments are successful, HTLC outputs are merged back to the main outputs? Meaning the HTLC portion of the commitment transaction rarely gets recorded on-chain?  
A: Yes, this correct. The RFCs state that each node should try to remove HTLCs as soon as possible. Leaving HTLCs in would increase fees in case of an uncooperative close.

### Breach Remedy

Q: When two parties exchange the previous commitment's secrets (to invalidate previous state), how do you make sure that the exchange happen atomically? (i.e., that both receive the other's secret, or none at all)  
A: It is not required to exchange the secrets atomically because the penalty transaction (breach remedy) can only be broadcast after the old state transaction is confirmed on-chain. I can safely share my secret as it is harmless unless I am the bad actor. If my counterparty refuses to disclose their secret, then the channel update will fail to transition to the next state, making the current state remain active and valid.

### Timelocks

Q: Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction spending the outputs when the script could check if the requirements are being met by itself?  
A: One reason is not needing to provide height in script interpreter and so allowing caching of the script verification. Another reason is that it allows other semantics in the fields (like eltoo).

Q: Can both CSV and CLTV be used in the same output and are there any known use cases for it?  
A: Yes, as they use different fields there shouldn't be conflict. A case could be an advanced form of vault.

Q: Is it fair to say UTXO-level timelocks are superior to tx-level timelocks since they are baked directly into the protocol and allow more flexiblity and control? Are transaction-level timelocks necessary (Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence)?  
A: UTXO-level timelocks are an encumbrance rule and must succeed for the transaction to be valid so in a sense are superior. Tx-level timelocks play a different role from utxo-level timelocks. a utxo-level timelock restricts the time period for which an output can be spent regardless of the timelock on the transaction which can be arbitrary. Say I wanted to send you bitcoins that could only be spent after Christmas, without a utxo-level timelock, I have no way of enforcing this. You could choose to sign and broadcast the transaction earlier but with a utxo-level timelock (CSV or CLTV), I can enforce when an output cannot be spent. From a validation viewpoint, if the nLockTime for a tx makes the tx invalid, there's no need to validate the scripts if they contain utxo-level timelocks.

### HTLCs and micropayments

Q: What do you think of the criticism that HTLCs don't work for micropayments?  
A: More information by [Dave Harding on Bitcoin StackExchange](https://bitcoin.stackexchange.com/questions/85650/htlcs-dont-work-for-micropayments/85694#85694)
