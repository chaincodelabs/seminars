# Some Responses to the Discussion Questions

### Rendezvous Routing
Q: Can someone breakdown Rendezvous into more basic language?  
A: **Problem:** Sender knows too much about the receiver when routing, since the sender has to select the route.  
**Solution:** To remain hidden the receiver decides on the last part of the route: He chooses a random, well connected node as a rendez-vous node RV (i.e. meeting point), where the sender should route to. The receiver passes encrypted routing information for the RV-node in the invoice. The RV-node encrypts the routing information and continues to route to the next hop. The next hop might be the receiver or just one hop on the route chosen by the receiver.

Q: Would it make sense to chain multiple rendezvous meeting points?  
A: The rendezvous node, even if it's a sybil of the sender, should only know the next hop. Onion routing should hide the rest of the route from the rendezvous node to the receiver.

### Neutrino
Q: If Neutrino becomes the preferred way of using Bitcoin, wouldn't it give too much power to the miners since Neutrino clients might blindly follow the longest chain in the case there is a fork? Should Neutrino be coupled with a trusted server (that runs a full node) by default? Should it be disabled by default in Bitcoin Core?  
A: Further [reading](https://medium.com/@nicolasdorier/neutrino-is-dangerous-for-my-self-sovereignty-18fac5bcdc25)

### Watchtower
Q: How do watchtowers work with non-advertised channels when part of the graph is not known? Or with Trampoline when routing calculation is outsourced?  
A: Channels are not relevant to watchtowers as they only need to watch the chain for specific closing transactions.
