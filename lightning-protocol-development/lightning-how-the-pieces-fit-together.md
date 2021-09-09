# How the layers of Lightning Fit Together

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [A walk through the layers of Lightning](https://btctranscripts.com/scalingbitcoin/tel-aviv-2019/edgedevplusplus/lightning-network-layer-by-layer/) | 30 |
| [Uncover the Lightning Network Transactions](https://medium.com/@yyforyongyu/till-its-lightning-fast-uncover-the-lightning-network-transactions-f3180e467857) | 20 |
| [The Update Layer](https://youtu.be/SoFlRCNdqDg) | 60 |
| [The Transfer Layer](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-24-fabrice-drouin-the-transfer-layer/) | 41 |
| [The Multihop Layer](https://youtu.be/P7I-C0_sijg) | 72 |
| [The other layers \(base and transport\)](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-24-fabrice-drouin-base-and-transport-layers-of-lightning-network/) | 17 |
| [Diffie–Hellman key exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) | 10 |
| [How and when do I use HMAC?](https://security.stackexchange.com/questions/20129/how-and-when-do-i-use-hmac) | 10 |

## Discussion Questions

1. How would an offline vending machine work?

### A walk through the layers of Lightning

1. How does the LN-Penalty mechanism currently leak out of the update layer?

### The Update Layer

1. How would switching to PTLCs affect the update layer?
2. If LN were to upgrade the update layer, to Eltoo for example, would the network need to end-to-end upgrade?
3. Would there ever be a reason to prefer LN-penalty when creating a channel between two Eltoo-capable nodes?
4. Why are the second stage HTLC transactions not part of the commitment transaction?

### The Transfer Layer

1. Explain how the timeout mechanism works for in-flight HTLCs?
2. How is the payment hash sent to the payer?
3. Can both HTLCs and PTLCs coexist in a channel?
4. What's are the required parts of invoices?

### The Multihop Layer

1. How can nodes that are not always online prevent loss of funds?
2. What are the risks of forwarding below-dust payments?
3. What is the relationship of the revocation keys for multiple subsequent commitment transactions? What would change if revocation keys were independent?
4. How can you send a payment to a node without getting an invoice? What are the tradeoffs of this payment method?
5. Why is a grace period added to the HTLC timeout?
6. What are routing hints and why are they important for private channels? Do they leak privacy?

### Diffie–Hellman key exchange

1. What is a Diffie-Hellman key exchange used for?

### How and when do I use HMAC?

1. What's the difference between a MAC and an HMAC?

