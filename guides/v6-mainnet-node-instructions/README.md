---
description: 'Last update: 2024-02-02'
---

# Node Instructions

#### The section below will guide you through installing a DKG node on NeuroWebAI. Please refer to the subsections to turn your current node into a multinode setup or installing a Gnosis node only.&#x20;

{% hint style="warning" %}
You need 50k [**teleported TRAC**](https://teleport.origintrail.io/) to run a V6 node on NeuroWeb AI. Teleport happens once a month on the 15th of each month and is a temporary measure while waiting for the common good Polkadot Parachain bridge, Snowbridge, built by [**Snowfork**](https://github.com/Snowfork/snowbridge)**.**
{% endhint %}

{% hint style="info" %}
If you want to delegate your TRAC rather than running your own node, staking will soon be available on Gnosis chain so stay tuned!
{% endhint %}

## Step 1 - Create a total of 4 wallets

You must create a total of 4 wallets for the first step.&#x20;

<table><thead><tr><th width="65" data-type="number">#</th><th width="266">Wallet</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>EVM Operational wallet</td><td>Hot wallet for non admin node operations<br>Example: Talisman, Metamask wallet</td></tr><tr><td>2</td><td>EVM Management wallet</td><td>Cold wallet for admin node operations where your TRAC is held<br>Example: Ledger</td></tr><tr><td>3</td><td>Substrate Operational wallet</td><td>Wallet to map with wallet #1<br>Example: polkadot.js, Talisman wallet</td></tr><tr><td>4</td><td>Substrate Management wallet</td><td>Wallet to map with wallet #2<br>Example: polkadot.js, Talisman wallet</td></tr></tbody></table>

{% hint style="warning" %}
Mapping a hardware EVM wallet (such as Ledger) to a hot substrate wallet (such as polkadot.js or Talisman wallet) could expose your funds to the Internet since both EVM and substrate wallets can have full access to your funds on the Polkadot Ecosystem. Ledger integration with parachains is in the works.
{% endhint %}

## Step 2 - Add the OriginTrail Mainnet Network onto MetaMask

Add the NeuroWeb Mainnet Network on your MetaMask client and switch to it.&#x20;

| Network name        | NeuroWeb Mainnet                                                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| **RPC URL**         | [https://astrosat-parachain-rpc.origin-trail.network/](https://astrosat-parachain-rpc.origin-trail.network/) |
| **Chain ID**        | 2043                                                                                                         |
| **Currency symbol** | MNEURO                                                                                                       |

## Step 3 - Fund your wallets with NEURO

There are currently 2 ways to fund your wallet with NEURO

1. Bridge ERC-20 TRAC from Ethereum using [**Portal Bridge**](https://portalbridge.com/) to Moonbeam, then use [**Stellaswap**](https://app.stellaswap.com/exchange/swap) to swap moonbeamTRAC to NEURO.&#x20;
2. Ask for some NEURO on [**OriginTrail Node Community**](https://t.me/otnodegroup)**.**&#x20;

You need at least 1 NEURO to keep your substrate wallet active and another NEURO for transaction fees (total: 2 NEURO). You need 2 NEURO on both of your substrate wallets (wallet **3 and 4** from step 1).

## Step 4 - Map your wallets

Mapping is a permanent method to link an EVM to a substrate wallet so actions on either chain will reflect on your mapped wallet.&#x20;

Once the funding of both substrate wallets are completed, head to the [**mapping interface**](https://parachain.origintrail.io/parachain-account-mapping) and select **Parachain Mainnet**.&#x20;

Your goal here is to map wallet **1 and** **3** together, and wallet **2 and 4** together from step 1.&#x20;

To do so, connect to the mapping interface with the appropriate MetaMask wallet and paste the corresponding substrate wallet. 2 pop-ups will follow and sign both transactions.

{% hint style="warning" %}
If mapping doesn't prompt you with 2 transactions, make sure you have at least 2 NEURO on your substrate wallet, try disabling all other extensions and restart your browser. You can also use a different browser. Choose between Chrome, Brave, Firefox.
{% endhint %}

Repeat for wallet **2 and 4** from step 1 and you would have completed the mapping process for your node.&#x20;

## Step 5 - Fund your management wallet with teleported TRAC

You require a minimum of 50k TRAC to run a mainnet node. You must fund your EVM Management wallet with the required amount (wallet 2). You can purchase TRAC on platforms such as [**Coinbase**](https://www.coinbase.com/price/origintrail)**,** [**Kucoin**](https://www.kucoin.com/trade/TRAC-BTC)**,** [**Binance US**](https://www.binance.us/trade/pro/TRAC\_usd)**,** [**Huobi**](https://www.huobi.com/en-us/exchange/trac\_usdt/) and [**Uniswap**](https://app.uniswap.org/#/swap?outputCurrency=0xaa7a9ca87d3694b5755f213b5d04094b8d0f0a6f) and once purchased, you need to [**teleport**](https://teleport.origintrail.io/) them to NeuroWeb. [OT-RFC-16](https://github.com/OriginTrail/OT-RFC-repository/blob/main/RFCs/OT-RFC-16-Parachain-Bridges-Implementation/OT-RFC-16-Parachain-Bridges-Implementation.pdf) is currently underway to determine how to bridge TRAC to the OT Parachain and back. &#x20;

{% hint style="info" %}
**Reminder**:&#x20;

NEURO is used as gas to send teleported TRAC so always have at least 2 NEURO on each wallet containing teleported TRAC.&#x20;
{% endhint %}

To view your TRAC balance on Metamask, first switch your network to NeuroWeb Network, then add the TRAC token address using the import function

```
0xFfFFFFff00000000000000000000000000000001
```

You can also view your teleported TRAC balance on [**Subscan**](https://neuroweb.subscan.io/).&#x20;

## Step 6 - Install your node

In order to deploy your OriginTrail V6 node on NeuroWeb, you will need a Linux (Ubuntu) server with the following minimum recommended hardware:

* **4GB RAM**
* **2CPUs**
* **50GB HDD space**

{% hint style="warning" %}
Log in to the server as root. You **cannot** use sudo and run this script.&#x20;
{% endhint %}

Gather the following information:

| Value                          | Description                           |
| ------------------------------ | ------------------------------------- |
| EVM\_OPERATIONAL\_WALLET       | Public address of wallet #1 in step 1 |
| EVM\_OPERATIONAL\_PRIVATE\_KEY | Private key of wallet #1 in step 1    |
| EVM\_MANAGEMENT\_WALLET        | Public address of wallet #2 in step 1 |
| SHARES\_TOKEN\_NAME            | Your choice of token name             |
| SHARES\_TOKEN\_SYMBOL          | The token symbol of your token name   |

**Run the one-liner installer script:**

```
cd /root/ && curl https://raw.githubusercontent.com/OriginTrail/ot-node/v6/release/mainnet/installer/installer.sh --output installer.sh && chmod +x installer.sh && ./installer.sh
```

{% hint style="danger" %}
You must choose a SQL password for the installer to work. Do not leave that field empty.
{% endhint %}

{% hint style="info" %}
**Reminder**:&#x20;

In order to use aliases to quickly check node logs, start/stop/restart node, change node config, you must execute the following script after the installation:

\
source \~/.bashrc



Once the sourcing is done, try the following:\
otnode-logs

otnode-start

otnode-stop

otnode-restart

otnode-config
{% endhint %}

#### You have now successfully completed your node installation! You can check the logs by using the alias otnode-logs.&#x20;

{% hint style="success" %}
### After successfully installing your V6 node on NeuroWeb, you can check out advanced network statistics on [OTHub.io](https://www.othub.io/) or by querying the Telegram [@othubbot](https://t.me/othubbot).
{% endhint %}

Even though your node is online, your node does not have any stake nor ask price, which will be covered on Step 7.&#x20;

{% hint style="warning" %}
#### You can either do Step 7A or 7B for the following section. 7A requires the use of  [Houston ](https://houston.origintrail.io/login) to set your stake and ask, while 7B uses your node command line interface.
{% endhint %}

## Step 7A - Houston

[**Houston V6 Node Command Center** ](https://houston.origintrail.io/)is an interface to help manage your node and view network statistics.&#x20;

First, log in with your management and operational EVM wallets;

Go to tab "Service Tokenomics";

Input your ask price and sign the transaction. The current average network ask is 0.01 TRAC/(epoch \* KB);

Input the amount of stake you want. Minimum stake is 50,000 TRAC;

Restart your node:

```
systemctl restart otnode
```

## Step 7B - Set-stake and set-ask

The installer above will only set up all the prerequisites and node files. You must run 2 scripts to create the node profile and set your service ask price.&#x20;

Gather the following information:

| Value                                  | Description                                                                                                                                                                                                                                                     |
| -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **EVM Operational wallet private key** | private key from wallet 1 in step 1                                                                                                                                                                                                                             |
| **EVM Management wallet private key**  | private key from wallet 2 in step 1                                                                                                                                                                                                                             |
| **Hub Contract Address**               | <p><strong>0x5fA7916c48Fe6D5F1738d12Ad234b78c90B4cAdA</strong><br>Check the official <a href="https://docs.origintrail.io/blockchain-layer-1/origintrail-parachain/deployed-smart-contracts"><strong>link</strong></a> to make sure it is the correct one. </p> |
| **Ask price**                          | Your price as a node runner to host assets, currently 0.01 TRAC/(epoch \* KB)                                                                                                                                                                                   |
| **rpcEndpoint**                        | [https://astrosat-parachain-rpc.origin-trail.network/](https://astrosat-parachain-rpc.origin-trail.network/)                                                                                                                                                    |
| **Stake**                              | <p>Your initial stake for your node <br>(minimum: 50,000)</p>                                                                                                                                                                                                   |

Navigate to the current ot-node version folder:

```
cd /root/ot-node/current
```

Once you have all the information above, run the following command by replacing the values in <> with the correct information (you can also change the other options if needed):

Set the **stake** of your node:

```
npm run set-stake -- --rpcEndpoint=https://astrosat-parachain-rpc.origin-trail.network/ --stake=50000 --operationalWalletPrivateKey=<private_key> --managementWalletPrivateKey=<private_key> --hubContractAddress=0x5fA7916c48Fe6D5F1738d12Ad234b78c90B4cAdA
```

Set the **service ask** of your node:

```
npm -C /root/ot-node/current run set-ask -- --rpcEndpoint=https://astrosat-parachain-rpc.origin-trail.network/ --ask=0.01 --privateKey=$(jq -r '.modules.blockchain.implementation.otp.config.evmOperationalWalletPrivateKey' /root/ot-node/.origintrail_noderc) --hubContractAddress=0x5fA7916c48Fe6D5F1738d12Ad234b78c90B4cAdA
```

Once you are done, restart the node:

```
systemctl restart otnode
```

{% hint style="success" %}
This is when your initial stake of 50k TRAC or above is sent from your initial wallet to your node profile contract.&#x20;
{% endhint %}

Check the logs, everything should be completed!

```
otnode-logs
```

{% hint style="info" %}
**Reminder:**

You can now use aliases such as otnode-logs to quickly view logs without having to type the entire string above!&#x20;
{% endhint %}
