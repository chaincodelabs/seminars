# Some Responses to the Discussion Questions

1. (a) Yes if you loose your channel state and your counterpart respond to you with an older `per_commitment_secret` in a `channel_reestablish` message you're likely going to use a revoked `per_commitment_point` for your next commitment transaction and then the malicious counterpart forces you to unilateral close the channel and it has already the secret to build justice txn on it. (b) If you use a watchtower which stores your commitment txn, but is not trustworthy.

### Breach Remedy
2. It is not required to exchange the secrets atomically because the penalty txn (breach remedy) can only be broadcast after the old state txn is confirmed on-chain. I can safely share my secret as it is harmless unless I am the bad actor. If my counterparty refuses to disclose their secret, then the channel update will fail to transition to the next state, making the current state remain active and valid.

### `CHECKSIGFROMSTACK`/`OP_PUSHTXDATA`
4. How can signature checks of arbitrary data be used to not have to store signatures for each channel state?

### Timelocks
5. One reason is not having to provide height in Script interpreter and so let you caching script verification. Another reason it lets you give other semantics to the fields (cf. eltoo).
6. Yes, as they use different fields there shouldn't be conflict. A case could be an advanced form of vault.
7. UTXO-level timelocks are an encumbrance rule and must succeed for the transaction to be valid so in a sense are superior. Tx-level timelocks play a different role from utxo-level timelocks. a utxo-level timelock restricts the time period for which an output can be spent regardless of the timelock on the transaction which can be arbitrary. Say I wanted to send you bitcoins that could only be spent after Christmas, without a utxo-level timelock, I have no way of enforcing this. You could choose to sign and broadcast the transaction earlier but with a utxo-level timelock (CSV or CLTV), I can enforce when an output cannot be spent. From a validation viewpoint, if the nLockTime for a tx makes the tx invalid, there's no need to validate the scripts if they contain utxo-level timelocks.
