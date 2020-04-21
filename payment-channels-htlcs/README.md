# Payment Channels, Intro to Lightning, and HTLCs

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Payment Channels](https://www.youtube.com/watch?v=4SdBa8ZOfqg) | 6 min | payment channels, primer, video |
[Understanding Payment Channels](https://blog.chainside.net/understanding-payment-channels-4ab018be79d4) | 10 min | payment channels |
[Revocable Transactions](https://rusty.ozlabs.org/?p=450) | 10 min | revocable transactions |
[Bitcoin timelocks in a nutshell](https://medium.com/@RobinHung/bitcoin-timelocks-in-a-nutshell-4c95aafc7a59) | 6 min | timelocks, primer |
[Bitcoin Timelocks Explained](https://medium.com/summa-technology/bitcoins-time-locks-27e0c362d7a1) | 16 min | timelocks |
[Hashed Timelock Contracts](https://rusty.ozlabs.org/?p=462) | 5 min | HTLCs |
[Visualizing HTLCs and the Lightning Network's Dirty Little Secret](https://medium.com/@peter_r/visualizing-htlcs-and-the-lightning-networks-dirty-little-secret-cb9b5773a0) | 10 min | HTLCs |
[HTLC implementation in the Core wallet](https://github.com/bitcoin/bitcoin/pull/7601) | 20 min | HTLCs |

## Discussion Questions

1. Given the fact that Lightning is punishment-based and that it requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds?

### Breach Remedy
2. When 2 parties exchange the previous commitment’s secrets (to invalidate prev state), how do you make sure that the exchange happen atomically? i.e., whether both receive the other’s secret, or none at all?

3. Related to (2), how do you exchange previous commitment's data if the parties aren't online on the same time?

### `CHECKSIGFROMSTACK`/`OP_PUSHTXDATA`
4. How can signature checks of arbitrary data be used to not have to store signatures for each channel state?

### Timelocks
5. Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction that is spending the outputs when the script could check the if the requirements are being met by itself?
6. Can both CSV and CLTV be used in the same Output and are there any known use cases for it?
"all nSequence locked transactions are opting into RBF": in general why do these 2 concepts (timelock & RBF) are mixed together? why can't a nSequence-locked tx opt out of RBF (but a nTimeLock-locked tx can)? was this intentional? what are the implications of this?
7. Is it fair to say UTXO-level timelocks are superior to tx-level timelocks? as they are baked directly into the protocol & allow more flexiblity/control. Are tx-level timelocks still necessary? (Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence)
