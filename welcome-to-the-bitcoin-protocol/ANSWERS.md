# Some Responses to the Discussion Questions

Q: Why did Satoshi put so much stress on the irreversibility of transactions?  
A: The system of electronic payments made with credit and with the possibility of transaction reversal introduces the need for more trust. It creates a system where the trusted third parties that facilitate payments (banks) are required to mediate disputes, which increases the cost to transact. Some fraud will always occur in such a system, further increasing costs. Bitcoin's creator wanted its payment system to be the digital equivalent of transacting with cash, where payments can't be reversed once sent. Thereby eliminating the need for trusted third parties to mediate disputes and the risk of being defrauded.

Q: What proposed role do SPV nodes play in the bitcoin ecosystem?  
A: SPV nodes have the ability to verify that a payment has been included in the blockchain, without bearing the costs of running a full node. An SPV node downloads and maintains a copy of the most-work chain's block headers, and can verify that a payment was included in a given block by querying peers for that block's Merkle branch data.

Q: How have show-stopping bugs or disruptions to the network been handled in the past?  
A: At one time, the community was small enough that Satoshi and early maintainers were able to simply make code changes, entice users to upgrade, and ask miners to do any reorganizing necessary to remedy major bugs, such one where a transaction was introduced in a block that caused an overflow.

Q: In your opinion, what did Satoshi "invent" that was truly innovative?  
A: One of Satoshi's key inventions was the minting and transferring of money in a non-reversible way by using Proof of Work.

Q: What is a Sybil Attack, and how has it been solved in the past?  
A: A Sybil attack is one where a nefarious actor creates enough fake nodes (one node pretending to be many) to take over a network's consensus mechanism. In the past, two possible ways of preventing Sybil Attacks were 1) to have a gatekeeper allowing entry into a network (which creates the need for trust and a single point of failure), or 2) to require each node in a network to periodically solve a Proof-of-Work puzzle; this would be no problem for honest nodes, but difficult for Sybil nodes. This latter strategy creates a scenario where honest nodes end up needing to run as many nodes as they can computationally afford, so that attackers don't gain a moderate advantage by have >1 identities while honest actors only claim 1.

Q: What is the "fair exchange" problem, and how does it apply to the blockchain?  
A: The fair exchange problem is the question of how to ensure that money is transferred only if an asset is transferred or a service is rendered in return. Smart contracts enable this kind of functionality in Bitcoin without the need for an arbitrator.

Q: Why do the authors of Bitcoin's Academic Pedigree believe that bitcoin was ignored by academia for a long time? What reputation/relationship does bitcoin have with academia today?  
A: The authors believe that academia has a resistance to radical ideas, which Bitcoin was, being that it was not formally peer reviewed and didn't provide much reference to previous work in related fields. The authors assert that academics have spent time in recent years ignoring Bitcoin or arguing why it can't work, despite the fact that it already does work. Today, Bitcoin remains somewhat unconnected from the disciplines that it's based on. For instance, ongoing Proof-of-Work research today continues without making reference to Bitcoin.

Q: How do you judge the merits or value of a good project/experiment?  
A:  

* If the main goal of a project is to market is to maximize the sales of its coin, it's not a good project; analogy being to that of a company whose only business plan is market its stock.
* Where are the principals of the project/business located? Are they named? Can you validate that they are who they say the are? What regulatory authorities oversee them?
* What legal recourse do you have in case of fraud?
* Is the company running the project incorporated? Do they have the appropriate licenses? Do they have a legal authority to issue stock?
* Basically, do diligence on projects as you would on a company.
