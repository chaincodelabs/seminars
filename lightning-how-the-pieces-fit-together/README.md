# How the layers of Lightning Fit Together

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[A walk through the layers of Lightning](https://diyhpl.us/wiki/transcripts/scalingbitcoin/tel-aviv-2019/edgedevplusplus/lightning-network-layer-by-layer/) | 30 min | LN layers |
[The Update Layer](https://youtu.be/SoFlRCNdqDg) | 60 min | update, video |
[The Transfer Layer](https://youtu.be/CGE8I8L7BAc) | 41 min | transfer, video |
[The Multihop Layer](https://youtu.be/P7I-C0_sijg) | 72 min | multihop, video |
[The other layers (base and transport)](https://youtu.be/wyri7cc83kQ) | 17 min | base, transport, video |
[Diffie–Hellman key exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) | 10 min | Diffie–Hellman, cryptography |
[How and when do I use HMAC?](https://security.stackexchange.com/questions/20129/how-and-when-do-i-use-hmac) | 10 min | HMAC, cryptography |

## Discussion Questions

1. How is the payment hash sent to the payer?
1. Explain how the timeout mechanism works for in-flight HTLCs?
1. How would an offline vending machine work?
1. What are routing hints and why are they important for private channels? Do they leak privacy?
1. How does the LN-Penalty mechanism currently leak out of the update layer?
1. If LN were to upgrade the update layer, to eltoo for example, would the network need to end-to-end upgrade?
