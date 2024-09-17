---
description: 'Last updated: 2024-09-06'
---

# Staking Instructions

## Step 1 - Choose where to stake

You have the option to choose between 3 networks to delegate your TRAC - Base chain, Gnosis chain or NeuroWeb AI.&#x20;

**Each chain has its pros and cons:**

* **Base chain** is relatively new and has the fewest amount of pubs. It takes 28 days to unstake your TRAC and another 7 days to withdraw your TRAC from Base chain to Ethereum chain.&#x20;
* **Gnosis chain** has the highest yield, but also the highest amount of delegators. Base chain and NeuroWeb AI are also expected to out scale Gnosis in terms of both performance and growth.&#x20;
* **NeuroWeb AI** is the official parachain by OriginTrail. It is the most scalable chain and the chain we expect to see the highest growth. It is also the most complex due to mapping process and teleportation. We expect bridging to be a lot easier once Snowbridge goes live, and we also recommend staking on this chain for future proofing.&#x20;

Once you selected your chain, you need to review the yield, the node operator, commission rates and if there is any available space on the node you want to stake to.&#x20;

{% hint style="info" %}
The APR displayed on the [official staking page](https://dkg.origintrail.io/staking) might be misleading as it shows the overall APR, not the latest APR which might be very different depending on node stake size. &#x20;
{% endhint %}

A common strategy is to stake on a well known community node, such as OTHub, and try to stake to a node that is almost filled up.&#x20;

## Step 2 - Add your chosen network to Metamask

### Gnosis

If you choose to stake on the Gnosis network, add it to your Metamask extension by either connecting Metamask here [**link** ](https://chainlist.org/?search=gnosis)or manually with the info below

| Network name        | Gnosis                                           |
| ------------------- | ------------------------------------------------ |
| **RPC URL**         | [https://1rpc.io/gnosis](https://1rpc.io/gnosis) |
| **Chain ID**        | 100                                              |
| **Currency symbol** | XDAI                                             |

Add Gnosis TRAC on MetaMask by importing this contract address. You will see your Gnosis TRAC once you complete Step 3.

```
0xEddd81E0792E764501AaE206EB432399a0268DB5
```

### NeuroWeb AI

If you choose to stake on the NeuroWeb AI network, add it to your Metamask manually with the info below

| Network name        | NeuroWeb Mainnet                                                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| **RPC URL**         | [https://astrosat-parachain-rpc.origin-trail.network/](https://astrosat-parachain-rpc.origin-trail.network/) |
| **Chain ID**        | 2043                                                                                                         |
| **Currency symbol** | MNEURO                                                                                                       |

Add Neuro TRAC on MetaMask by importing this contract address. You will see your Neuro TRAC once you complete Step 3.

```
0xFfFFFFff00000000000000000000000000000001
```

### Base chain

If you choose to stake on the Base network, add it to your Metamask manually with the info below

| Network name        | Base                                                 |
| ------------------- | ---------------------------------------------------- |
| **RPC URL**         | [https://mainnet.base.org](https://mainnet.base.org) |
| **Chain ID**        | 8453                                                 |
| **Currency symbol** | ETH                                                  |

Add Base TRAC on MetaMask by importing this contract address. You will see your Base TRAC once you complete Step 3.

```
0xA81a52B4dda010896cDd386C7fBdc5CDc835ba23
```

## Step 3 - Fund your wallet

### Gnosis Chain

Begin by obtaining xDAI for operations on Gnosis chain through their [**faucet**](https://www.gnosisfaucet.com/). If the wallet is down, you can try the [**Jumper**](https://jumper.exchange/) to swap any assets to xDAI on Gnosis. If Ethereum gas fee is high, you can request 0.01 xDAI **if you are going to stake on OTHub nodes** at our [**Telegram**](https://t.me/othubio).

{% hint style="info" %}
Since Gnosis is EVM compatible, you can use your Ledger connected to MetaMask for all operations to keep your funds safe. Connect your Ledger to MetaMask using these [**instructions**](https://support.ledger.com/hc/en-us/articles/4404366864657-Connect-your-Ledger-to-MetaMask?docs=true).
{% endhint %}

Once you obtained xDAI, bridge your ERC-20 TRAC from Ethereum to Gnosis by using the [**Omnibridge**](https://omnibridge.gnosischain.com/bridge). Switch your MetaMask network to Gnosis as configured on Step 1, then input the amount of TRAC you want to bridge. You will have to Unlock (first transaction) then Transfer (second transfer) to bridge your TRAC. The transaction can take up to an hour, and even if you close the window, you will eventually receive your TRAC on Gnosis chain.

<figure><img src="../.gitbook/assets/image (31).png" alt="" width="337"><figcaption></figcaption></figure>

{% hint style="warning" %}
There is no fee for bridging assets to Gnosis other than regular gas fee. However, there is a 0.1% cut on your assets when you bridge assets back to Ethereum from Gnosis.
{% endhint %}

{% hint style="warning" %}
If your TRAC is currently teleported on NeuroWeb AI (formerly known as OriginTrail parachain), you need to [**teleport**](https://teleport.origintrail.io/) them back to Ethereum before you can stake on Gnosis.&#x20;
{% endhint %}

### NeuroWeb AI

There are some extra steps if you want to stake with NeuroWeb AI, as you need to map your EVM wallet to your substrate (Polkadot) wallet. You also need to use the monthly [teleport ](https://teleport.origintrail.io)to get TRAC across to NeuroWeb AI, rather than using a bridge which is instant. A bridge, Snowbridge, update is coming to facilitate this process.  You will need to follow the [teleportation guide](trac-teleportation-faq.md).

{% hint style="warning" %}
You must send your tokens to the teleport contract before the 10th of each month and the teleport will happen on the 15th.
{% endhint %}

Once you have TRAC on NeuroWeb AI, you also need 2 NEURO tokens, which can be obtained on StellaSwap, Gate.io or MEXC.&#x20;

### Base Chain

Base chain uses Ethereum (ETH) for gas. So you will need to bridge some ETH across to cover the gas to stake by using [SuperBridge](https://superbridge.app/base).

Once you have bridged some ETH across, you will also need to bridge TRAC using the same SuperBridge.

{% hint style="info" %}
Since Base is EVM compatible, you can use your Ledger connected to MetaMask for all operations to keep your funds safe. Connect your Ledger to MetaMask using these [**instructions**](https://support.ledger.com/hc/en-us/articles/4404366864657-Connect-your-Ledger-to-MetaMask?docs=true).
{% endhint %}

## Step 4 - Stake

{% hint style="info" %}
A node can be fully operational with delegated stake only as long as the total stake amount is 50k TRAC or above. If the node you add your stake to has less than 50k TRAC, it will not be earning any publishes. The higher the stake of a node compared to other nodes on the same network, the more it will earn.
{% endhint %}

Visit the [**staking dashboard**](https://dkg.origintrail.io/staking) and connect to your Metamask.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Select the node to delegate your TRAC and input the amount you want to stake. You need to confirm 2 transactions.

{% hint style="warning" %}
Note that delegated stake sent to a node will lock your TRAC for 28 days for Gnosis and Base chain, and 5 minutes for NeuroWeb AI (this might change once Snowbridge support goes live).
{% endhint %}

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
If you are staking a large amount, you might have to manually increase the gas by adding an extra 0 to the gas limit in the advanced settings on MetaMask on the second transaction. See picture below.
{% endhint %}

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

### You have now successfully staked your TRAC!

{% hint style="success" %}
#### The editor of OTHub Deep Dive, BRX, is a long time community admin of OriginTrail and a 4+ year node runner on the network. BRX is also part of team OTHub, an open source community driven project providing network analytics, node statistics and an API to everyone for free. To keep OTHub servers running and to keep providing Deep Dive with the latest content, we appreciate any stake you could delegate to our OTHub, OTHub2 or OTHub3 node.

#### Please visit [https://othub.io/staking](https://othub.io/staking) for more details!
{% endhint %}
