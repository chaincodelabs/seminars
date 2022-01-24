# The Future of Lightning

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Breaking Down the Bitcoin Lightning Network: eltoo](https://medium.com/@brandonarvanaghi/breaking-down-the-bitcoin-lightning-network-eltoo-c48554f5ae02) | 11 |
| [Eltoo and the Far Future](https://btctranscripts.com/chaincode-labs/2019-09-18-christian-decker-eltoo/) | 30 |
| \(_optional_\) [Onion Messages](https://github.com/lightning/bolts/pull/759) | X |
| [Offers](https://bitcoinops.org/en/topics/offers/) (proposed BOLT12) | 5 |
| \(_optional_\) [Route Blinding](https://github.com/lightning/bolts/pull/765) | X |
| [Submarine Swaps](http://btctranscripts.com/magicalcryptoconference/2019/submarine-swaps/) | 5 |
| [Loops](https://blog.lightning.engineering/posts/2019/03/20/loop.html) | 5 |
| \(_optional_\) [Submarine swaps/ Loops](https://youtu.be/qixhNBIHDyE) | 42 |
| [Splicing](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-26-rene-pickhardt-splicing/) | 22 |
| [Dual funded channels](https://www.youtube.com/watch?v=i_GxmNZjwhk) (until min 26) | 26 |
| [Liquidity Advertisements](https://medium.com/blockstream/lightnings-missing-piece-a-decentralized-liquidity-market-a0bb47534a4f) | 6 |
| [Multi-party channels/Channel factories](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-28-christian-decker-multiparty-channels/) | 13 |
| [Payment Points: Replacing HTLCs](https://suredbits.com/payment-points-part-1/) | 10 |
| [Payment Points: "Stuckless" Payments](https://suredbits.com/payment-points-part-2-stuckless-payments/) | 10 |
| [Peer Backups](https://medium.com/@ACINQ/phoenix-wallet-part-3-backup-f63a9470d4e7) | 5 |
| \(_optional_\) [Minisketch and lightning gossip](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-December/001741.html) | X |

## Discussion Questions

### Breaking Down the Bitcoin Lightning Network: eltoo

1. Why do we need SIGHASH\_NOINPUT for eltoo?
2. What do HTLCs look like for an Eltoo channel?

### Eltoo and the Far Future

1. How does a cooperative close work with Eltoo?
2. Can channels using Eltoo or PTLC be mixed with standard channels in a multi-hop payment?
3. Would there ever be a reason to prefer LN-penalty when creating a channel between two Eltoo-capable nodes?

### Submarine swaps

1. Can an adversary make a swap and then wait until a moment before the lock expiry to reveal the secret on one chain while using the signature on the other? If the blocks are fast, could an attacker be able to steal the money from both chains?

### Splicing

1. Is it easier to splice on an Eltoo channel?

### Multi-party channels/Channel factories

1. What are the advantages and disadvantages of multiparty channels?

### Dual funded channels

1. How do you split the fees in dual-funded channels?

### Payment Points: Replacing HTLCs

1. How does a wormhole attack work?
2. Can sender or receiver notice a wormhole attack?
