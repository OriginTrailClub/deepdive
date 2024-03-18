---
description: Explaining the utility of TRAC token in details
---

# TRAC Utility Mechanics

The mechanics of TRAC within the OriginTrail ecosystem are designed to ensure a transparent, efficient, and decentralized knowledge economy. Here’s a breakdown of the key components:

## Publishing Mechanics

The publisher, such as a poultry producer wishing to showcase their farm’s certifications and practices, determines the length of the service in terms of epoch (1 epoch = 90 days), sets a bid price, and the asset is measured by size (1 byte per character).&#x20;

The service cost in $TRAC is calculated as follows:

$$
Service cost ($TRAC) = Bid Price * Asset Size (KB) * Number of Epochs * Number of Nodes
$$

Number of Nodes: 3 (always 3 winning nodes per asset published per epoch)

#### Example:

If a poultry producer wishes to publish a Knowledge Asset of 10KB for 2 epochs, at a bid price of 0.02 $TRAC, the calculation is:

$$
Service cost = 0.02 * 10 * 2 * 3 = 1.2 TRAC
$$

## Node Operation and Staking Mechanics

To begin accepting services, OriginTrail node runners must stake a minimum of 50,000 TRAC. This acts as collateral to foster reliability and integrity. Nodes set an ask price, which is the minimum they are willing to accept for storing assets. The bid from publishers must meet or exceed this ask price to ensure their assets are stored.

Nodes are selected based on their 'score', determined by their proximity to the asset and the amount of TRAC they have staked.

$$
Node score = Distance + Node stake
$$

## Node Selection and Reward Process:

Every epoch, 3 nodes are chosen based on the highest scores to submit storage proofs. If successful, they receive a reward. The process ensures that only the most reliable nodes store the Knowledge Assets.

## Delegator Earnings and Fees:

TRAC holders have the option to delegate their stake to node runners, sharing in the earnings without managing a node. Earnings for delegators are calculated based on the proportion of their stake to the total node stake, minus any operator fees for node maintenance and expenses.

$$
Delegator earnings = TRAC won * (delegator share / total node stake) * (1 - op fee)
$$

#### Example:

If you delegate 200,000 TRAC to a node with a total stake of 2 million TRAC, and the node wins a reward of 400,000 TRAC (representing a 20% APY) with a 10% operator fee:

$$
Delegator earnings = 400,000 * (200,000/2,000,000) * (1 - 0.1) = 36,000 TRAC
$$

$$
Operator fee = 400,000 * 0.1 = 40,000 TRAC
$$

This model encourages active participation within the ecosystem, promotes the reliability of asset storage, and ensures a fair distribution of rewards based on contribution and performance.

\
