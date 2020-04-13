# Some Responses to the Discussion Questions

### Channel rebalancing
3.  In my opinion, LN devs are leaving this task for higher level tooling software. It is currently possible to accomplish this using the available RPC's in LND or a c-lightning plugin. Links [here](https://lntoolkit.com/commands/auto-balance) and [here](https://github.com/bitromortac/lndmanage).
4. Opening a channel starts with all of the balance on your side, only allowing you to send payments. Loop Out shifts the channel balance to the other side allowing you to receive payments.

### Routing
5. Explain the concept of a shadow route.
6. Dijkstra's is faster, but cannot handle negative edge weights (payment channels that pay you to route through them). You can't get around this by simply normalizing the weights, you need BF or some other modification of it to handle the negative edges. [Link](https://medium.com/@rusty_lightning/routing-dijkstra-bellman-ford-and-bfg-7715840f004).

### Watchtower
11. Channels are not relevant to watchtowers as they only need to watch the chain for specific closing transactions.

### HTLC
12. Yes, this correct. The RFCs state that each node should try to remove HTLCs as soon as possible. Leaving HTLCs in would increase fees in case of an uncooperative close.
