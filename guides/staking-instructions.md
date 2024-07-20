---
description: 'Last updated: 2024-03-17'
---

# Staking Instructions

{% hint style="info" %}
Delegated staking is live on Gnosis, NeuroWebAI (OriginTrail Parachain) and Base.&#x20;
{% endhint %}

## Step 1 - Choose where to stake

Review the yield, commmission rates and if there is available space on the node you want to stake to. Try to stake to a node that is comparitively filled compared to other nodes on the same network. If the stake is too low it won't earn yield in compared with nodes on that network with higher stake.

## Step 2  - Add your chosen network to Metamask

Gnosis:

If you choose to stake on the Gnosis network, add it to your Metamask extension by either connecting Metamask here [**link** ](https://chainlist.org/?search=gnosis) or manually with the info below

| Network name        | Gnosis                                           |
| ------------------- | ------------------------------------------------ |
| **RPC URL**         | [https://1rpc.io/gnosis](https://1rpc.io/gnosis) |
| **Chain ID**        | 100                                              |
| **Currency symbol** | XDAI                                             |

Add Gnosis TRAC on MetaMask by importing this contract address. You will see your Gnosis TRAC once you complete Step 3.&#x20;

```
0xEddd81E0792E764501AaE206EB432399a0268DB5
```
NeuroWebAI:

If you choose to stake on the Neuro network, add it to your Metamask  manually with the info below

| Network name        | NeuroWeb                                                                                                     |
| ------------------- | ------------------------------------------------                                                             |
| **RPC URL**         | [https://astrosat-parachain-rpc.origin-trail.network/](https://astrosat-parachain-rpc.origin-trail.network/) |
| **Chain ID**        | 2043                                                                                                         |
| **Currency symbol** | NEURO                                                                                                        |
Add Neuro TRAC on MetaMask by importing this contract address. You will see your Gnosis TRAC once you complete Step 3.&#x20;

```
0xFfFFFFff00000000000000000000000000000001
```
Base:

If you choose to stake on the Base network, add it to your Metamask  manually with the info below

| Network name        | Base                                                |
| ------------------- | ------------------------------------------------    |
| **RPC URL**         | [https://mainnet.base.org](https://mainnet.base.org)|
| **Chain ID**        | 8453                                                |
| **Currency symbol** | ETH                                                 |

Add Base TRAC on MetaMask by importing this contract address. You will see your Base TRAC once you complete Step 3.&#x20;

```
0xA81a52B4dda010896cDd386C7fBdc5CDc835ba23
```
## Step 3 - Fund your wallet

Gnosis:

Begin by obtaining xDAI for operations on Gnosis chain through their [**faucet**](https://www.gnosisfaucet.com/). If the wallet is down, you can try the [**Jumper**](https://jumper.exchange/) to swap any assets to xDAI on Gnosis. If Ethereum gas fee is high, you can request 0.01 xDAI **if you are going to stake on OTHub nodes** at our [**Telegram**](https://t.me/othubio).&#x20;

{% hint style="info" %}
Since Gnosis is EVM compatible, you can use your Ledger connected to MetaMask for all operations to keep your funds safe. Connect your Ledger to MetaMask using these [**instructions**](https://support.ledger.com/hc/en-us/articles/4404366864657-Connect-your-Ledger-to-MetaMask?docs=true).&#x20;
{% endhint %}

Once you obtained xDAI, bridge your ERC-20 TRAC from Ethereum to Gnosis by using the [**Omnibridge**](https://omnibridge.gnosischain.com/bridge). Switch your MetaMask network to Gnosis as configured on Step 1, then input the amount of TRAC you want to bridge. You will have to Unlock (first transaction) then Transfer (second transfer) to bridge your TRAC. The transaction can take up to an hour, and even if you close the window, you will eventually receive your TRAC on Gnosis chain.&#x20;

<figure><img src="../.gitbook/assets/image (31).png" alt="" width="337"><figcaption></figcaption></figure>

{% hint style="warning" %}
There is no fee for bridging assets to Gnosis other than regular gas fee. However, there is a 0.1% cut on your assets when you bridge assets back to Ethereum from Gnosis.
{% endhint %}

{% hint style="warning" %}
If your TRAC is currently teleported on NeuroWeb AI (formerly known as OriginTrail parachain), you need to [**teleport**](https://teleport.origintrail.io/) them back to Ethereum before you can stake on Gnosis. You must send your tokens to the teleport contract before the 10th of each month and the teleport will happen on the 15th.&#x20;
{% endhint %}

NeuroWebAi:

There are some extra steps if you want to stake with NeuroWebAi, as you need to map your Eth wallet to your Polkadot wallet. You also need to use the monthly teleport to get Trac across to NeuroWebAI, rather than using a bridge which is instant. There is a bridge being developed called Snowbridge, but for now teleport is required. You will need to follow the teleportion guide here: [https://github.com/OriginTrailClub/deepdive/blob/main/guides/trac-teleportation-faq.md](https://github.com/OriginTrailClub/deepdive/blob/main/guides/trac-teleportation-faq.md). 

{% hint style="warning" %}
You must send your tokens to the teleport contract before the 10th of each month and the teleport will happen on the 15th.&#x20;
{% endhint %}

Once you have Trac on NeuroWebAI, you also need Neuro token. This can be obtained on StellaSwap, but more easily from a central exchange like Gate.io or Mexc.

{% hint style="info" %}
Since Gnosis is EVM compatible, you can use your Ledger connected to MetaMask for all operations to keep your funds safe. Connect your Ledger to MetaMask using these [**instructions**](https://support.ledger.com/hc/en-us/articles/4404366864657-Connect-your-Ledger-to-MetaMask?docs=true).&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (31).png" alt="" width="337"><figcaption></figcaption></figure>

Base:

Base chain uses Ethereum (ETH) for gas. So you will need to bridge some eth across to cover the gas to stake. You will need to use the SuperBridge [https://superbridge.app/base](https://superbridge.app/base)

Once you have bridged some Eth across, you will also need to bridge the Trac you want to stake. Again use the Superbridge.

{% hint style="info" %}
Since Base is EVM compatible, you can use your Ledger connected to MetaMask for all operations to keep your funds safe. Connect your Ledger to MetaMask using these [**instructions**](https://support.ledger.com/hc/en-us/articles/4404366864657-Connect-your-Ledger-to-MetaMask?docs=true).&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (31).png" alt="" width="337"><figcaption></figcaption></figure>

## Step 4 - Stake

{% hint style="info" %}
A node can be fully operational with delegated stake only as long as the total stake amount is 50k TRAC or above. If the node you add your stake to has less than 50k TRAC, it will not be earning any publishes. The higher the stake of a node compared to other nodes on the same network, the more it will earn.
{% endhint %}

Visit the [**staking dashboard**](https://dkg.origintrail.io/staking) and connect to your Metamask.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Select the node to delegate your TRAC and input the amount you want. You need to confirm 2 transactions.

{% hint style="warning" %}
Note that delegated stake sent to a node will lock your TRAC for 28 days.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
If you are staking a large amount, you might have to manually increase the gas by adding an extra 0 to the gas limit in the advanced settings on MetaMask on the second transaction. See picture below.
{% endhint %}

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

### You have now successfully staked your xTRAC!&#x20;

{% hint style="success" %}
### The editor of OriginTrail Deep Dive, BRX, is a long time community admin of OriginTrail and a 3+ year node runner on the network. BRX is also part of team OTHub, an open source community driven project providing network analytics, node statistics and an API to everyone for free. To keep OTHub servers running and to keep providing Deep Dive with the latest content, we appreciate any stake you could delegate to our OTHub, OTHub2 or OTHub3 node.

### Please visit [https://othub.io/staking](https://othub.io/staking) for more details!
{% endhint %}
