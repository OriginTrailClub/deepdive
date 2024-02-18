---
description: 'Last updated: 2024-02-15'
---

# Staking Instructions

{% hint style="info" %}
Delegated staking is live on Gnosis mainnet. Delegated staking on NeuroWebAI (formerly known as OriginTrail Parachain) will go live at a later date.&#x20;
{% endhint %}

## Step 1 - Add Gnosis Network to MetaMask

Begin by adding the Gnosis network to your Metamask extension by either connecting MetaMask to this [**link** ](https://chainlist.org/?search=gnosis)or manually with the info below

| Network name        | Gnosis                                           |
| ------------------- | ------------------------------------------------ |
| **RPC URL**         | [https://1rpc.io/gnosis](https://1rpc.io/gnosis) |
| **Chain ID**        | 100                                              |
| **Currency symbol** | XDAI                                             |

Add Gnosis TRAC on MetaMask by importing this contract address. You will see your Gnosis TRAC once you complete Step 2.&#x20;

```
0xEddd81E0792E764501AaE206EB432399a0268DB5
```

## Step 2 - Fund your wallet

Begin by obtaining xDAI for operations on Gnosis chain through their [**faucet**](https://www.gnosisfaucet.com/).&#x20;

If the faucet is not working, you can use the [**Jumper**](https://jumper.exchange/) to swap any assets to xDAI on Gnosis. If Ethereum gas fee is high, try to do your transactions on the weekend at nighttime.&#x20;

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

## Step 3 - Stake

{% hint style="info" %}
A node can be fully operational with delegated stake only as long as the total stake amount is 50k TRAC or above. If the node you add your stake to has less than 50k TRAC, it will not be earning any publishes.
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
### The editor of OriginTrail Deep Dive, BRX, is a long time community admin of OriginTrail and a 3+ year node runner on the network. BRX is also part of team OTHub, an open source community driven project providing network analytics, node statistics and an API to everyone for free. To keep OTHub servers running and to keep providing Deep Dive with the latest content, we appreciate any stake you could delegate to our OTHub or OTHub2 node.

### Contract addresses: 0xc5D08540bD854910Af9a5FfA53C4996Be8A794EC

### 0xbf4ff4760116a9Fd20933f976BD38281bEe42053

### Please visit [https://othub.io/staking](https://othub.io/staking) for more details!
{% endhint %}
