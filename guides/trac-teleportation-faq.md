---
description: 'Last updated: 2024-01-31'
---

# Teleportation Guide

## Instructions

#### **1. Teleport your TRAC**

First, consult the [**FAQ** ](trac-teleportation-faq.md#faq)section below to learn about Teleporting TRAC.

Once you are ready, teleport your TRAC by visiting [**this**](https://teleport.origintrail.io/) website. Make sure you read the steps thoroughly. Once you complete the 2 teleport transactions, your TRAC will leave your wallet and be locked on the smart contract, while NeuroWeb TRAC will be minted and sent to you as soon as ready.

#### **2. Collect NEURO bounty (expired)**

For earlier teleporters only, visit [**this**](https://teleport.origintrail.io/teleport-reward-claim) website to collect your NEURO bounty for teleporting. Make sure you use the same EVM (Ethereum) wallet you used to teleport TRAC on step 1. Then, paste a self-custody substrate (Polkadot) wallet of your choice to obtain your NEURO bounty. You can use the substrate wallet address starting with 1,5 or g. **Do not use a Ledger Polkadot wallet** as it is not yet compatible with NeuroWeb. You can easily create a substrate hot wallet by using [**Polkadot js extension**](https://polkadot.js.org/extension/) or [**Talisman**](https://talisman.xyz/)**.** The bounty will be sent out shortly.

#### 3. Map your wallets

You need to visit [**this**](https://parachain.origintrail.io/parachain-account-mapping) interface to map your EVM (Ethereum) wallet to your substrate (Polkadot) wallet in order to receive NeuroWeb TRAC.

If you want to know why mapping is mandatory, read [**this**](https://docs.origintrail.io/blockchain-layer-1/origintrail-parachain/origintrail-parachain-evm) description by OriginTrail team.

{% hint style="warning" %}
The mapping process is **permanent** so make sure you are using the right addresses.
{% endhint %}

On MetaMask, connect to the **NeuroWeb network** and use the correct RPC URL as noted [**here**](https://deepdive.origintrail.club/guides/v6-mainnet-node-instructions#step-2-add-the-origintrail-mainnet-network-onto-metamask).

{% hint style="info" %}
**Make sure you have at least 2 NEURO on your substrate wallet before mapping**. You are required to always hold at least 1 NEURO to keep your wallet active and some more NEURO for transactions.
{% endhint %}

On the mapping interface, select **Mainnet** from the drop down menu, click on **Connect wallet**, and paste your substrate wallet address starting with 1,5 or g, confirm both transactions and you are done!

Here is a short video by the OriginTrail team to help you with mapping your wallets:

{% embed url="https://youtu.be/yltbdB1bpEA" %}

#### 4. Retrieve your teleported TRAC

You can follow this [**link** ](https://teleport.origintrail.io/trac-distribution)to see your teleport status. Users who mapped their wallets successfully should see their teleported TRAC on their EVM wallet. Users who did not map their EVM wallet as shown on step 3 will have their teleported TRAC withheld until the mapping is completed. Teleported TRAC is airdropped automatically to your mapped wallet as soon as ready.

{% hint style="success" %}
If you have completed all previous steps, please import the NeuroWeb TRAC token to your Metamask address:

0xFfFFFFff00000000000000000000000000000001
{% endhint %}

## FAQ

**What does Teleporting TRAC mean exactly ?**

Teleporting TRAC involves locking your ERC-20 TRAC on Ethereum blockchain in a Smart Contract in order to mint the equivalent amount of TRAC on NeuroWeb to be used on the DKG v6 for many different applications - check illustration [here](https://teleport.origintrail.io/) and [OT-RFC-14](https://medium.com/origintrail/ot-rfc-14-dkg-v6-trac-tokenomics-886ff2b6b8cb?source=rss-fecf7416927e------2) for all use cases.

There was an elaborate RFC that was discussed in detail [here](https://github.com/OriginTrail/OT-RFC-repository/issues/16). The revised version of the RFC was approved and shown [here](https://medium.com/origintrail/ot-rfc-12-v2-teleporting-trac-to-the-origintrail-parachain-on-polkadot-de535a9d2693)

In summary, it was deemed risky to use a third-party bridge to bridge a large amount of our ERC-20 TRAC over to NeuroWeb. In case of a bridge hack, such as the recent [Nomad bridge hack](https://mobile.twitter.com/i/events/1554556780239355905), we would risk losing all bridged TRAC assets forever.

That is why the team, alongside the community, decided to use **Teleportation** in order to safely move ERC-20 TRAC over to NeuroWeb, using a smart contract that was thoroughly audited last year during [SFC staking](https://t.co/NYLru2Aqor).

#### **What are the benefits of Teleporting TRAC ?**

You can use NeuroWeb TRAC to run nodes and create knowledge assets.

#### **Teleportation step 4/4 shows “something went wrong, try again”. Did the transaction fail ?**

No, this is most likely a GUI error and not a transaction error. If you were able to confirm the transaction on Metamask and your TRAC is no longer in your wallet, it means the transaction was successful. If the Metamask transaction failed and your TRAC is still in your wallet. Try repeating the steps again after reopening your browser / using incognito mode.

You can verify the transaction by checking your Metamask history or using [this explorer](https://etherscan.io/) and inputting your wallet address to see where your TRAC currently is.

#### **What will happen to my TRAC if I don't teleport ?**

Nothing. TRAC will remain an ERC-20 Token. The Teleportation smart contract is only for those who want to use TRAC on NeuroWeb and is a temporary measure while waiting for Polkadot's first party Snowbridge.

#### **I have teleported my TRAC, where is my NeuroWeb TRAC now ?**

Please be patient and rest assured that the team will deliver your freshly minted NeuroWeb TRAC as soon as it's ready!

#### **How long is the Teleportation lock up period ?**

The lock period is over. Teleportation now works both ways and happens once a month on the 15th of each month.

#### **Can I use my Ledger/Trezor to teleport my TRAC ?**

Absolutely. I would go as far to say that is my recommended method of teleporting your TRAC to keep your funds safe.

NeuroWeb is EVM compatible and Metamask will be used extensively (as is the case now).

#### How do I check whether my mapping was successful ?

In order to verify whether your substrate address is mapped to a given EVM address, go to this [**link** ](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Flofar.origin-trail.network#/chainstate)if you mapped using Devnet, or this [**link** ](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fparachain-rpc.origin-trail.network#/chainstate)if you mapped using Mainnet.

1. Go to Developer > Storage tab
2. Choose evmAccounts ->accounts(H160)
3. Enter your EVM public key
4. Press + on the right side
5. You should get your substrate public address as a response

**If your question isn't covered here, check out the current official FAQ at the bottom of** [**https://teleport.origintrail.io/**](https://teleport.origintrail.io/) **or feel free to message me @BRX86 on any OriginTrail Telegram channels.**
