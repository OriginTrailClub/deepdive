---
description: 'Last updated: 2024-02-02'
---

# Multichain setup



{% hint style="info" %}
OriginTrail DKG V6 nodes are chain agnostic. You can set up one node on a server and use the same node on different blockchains. Each chain requires 50k TRAC to activate the node on that chain and to start submitting commits (winning assets).&#x20;

\
Example:\
To run a node that submits commits on both NeuroWebAI and Gnosis, you will require:

* 50k TRAC on NeuroWebAI + 2 NEURO for gas
* 50k TRAC on Gnosis + GNO for gas

The delegated stake can come from you or someone else.
{% endhint %}

{% hint style="info" %}
The DKG V6 on Gnosis is expected to go live in mid February 2024 alongside delegated staking. Delegated staking on NeuroWebAI will come at a later time.&#x20;
{% endhint %}

The guide below is for running a node on Gnosis chain.&#x20;

## Step 1 - Preparations

Begin by obtaining xDAI for operations on Gnosis chain through their [f**aucet**](https://www.gnosisfaucet.com/).&#x20;

Gnosis is EVM compatible. Therefore, you can use your Ethereum wallet on MetaMask or Ledger for all operations.

If you want to delegate to your own node, bridge your ERC-20 TRAC from Ethereum to Gnosis by using the [**Omnibridge**](https://omnibridge.gnosischain.com/bridge).&#x20;

{% hint style="info" %}
A node can be fully operational with delegated stake only as long as the total stake amount is 50k TRAC or above.
{% endhint %}

## Step 2 - Configurations

Head to your node config with the alias

```
otnode-config
```

or manually

```
nano ~/ot-node/.origintrail_noderc
```

Then, add the following to your config file

```
"gnosis:100": {
  "enabled": true,
  "config": {,
    "rpcEndpoints": [
      "https://rpc.chiado.gnosis.gateway.fm"
    ],
    "gasPriceOracleLink": "https://blockscout.chiadochain.net/api/v1/gas-price-oracle",
    "evmOperationalWalletPublicKey": "0x0bf...",
    "evmOperationalWalletPrivateKey": "0x1e3...",
    "evmManagementWalletPublicKey": "0xd09...",
    "sharesTokenSymbol": "symbol...",
    "sharesTokenName": "name..."
   }
 }
```

The end result should look like this. Double check for syntax errors!

```
{
  "modules": {
    "blockchain": {
      "defaultImplementation": "otp",
      "implementation": {
        "otp:2043": {
          "config": {
            "evmOperationalWalletPublicKey": "0x0bf...",
            "evmOperationalWalletPrivateKey": "0x1e3...",
            "evmManagementWalletPublicKey": "0xd09...",
            "sharesTokenSymbol": "symbol...",
            "sharesTokenName": "name..."
          }
        },
        "gnosis:100": {
          "enabled": true,
          "config": {
            "rpcEndpoints": [
              "https://rpc.chiado.gnosis.gateway.fm"
            ],
            "gasPriceOracleLink": "https://blockscout.chiadochain.net/api/v1/gas-price-oracle",
            "evmOperationalWalletPublicKey": "0x0bf...",
            "evmOperationalWalletPrivateKey": "0x1e3...",
            "evmManagementWalletPublicKey": "0xd09...",
            "sharesTokenSymbol": "symbol...",
            "sharesTokenName": "name..."
          }
        }
      }
    },
    "tripleStore": {
      "implementation": {
        "ot-blazegraph": {
          "enabled": true,
          "package": "./triple-store/implementation/ot-blazegraph/ot-blazegraph.js",
          "config": {
            "repositories": {
              "privateCurrent": {
                "url": "http://localhost:9999",
                "name": "private-current",
                "username": "admin",
                "password": ""
              },
              "privateHistory": {
                "url": "http://localhost:9999",
                "name": "private-history",
                "username": "admin",
                "password": ""
              },
              "publicCurrent": {
                "url": "http://localhost:9999",
                "name": "public-current",
                "username": "admin",
                "password": ""
              },
              "publicHistory": {
                "url": "http://localhost:9999",
                "name": "public-history",
                "username": "admin",
                "password": ""
              }
            }
          }
        }
      }
    }
  }
}
```

ctrl+x and ctrl+s to save and restart your node

```
otnode-restart && otnode-logs
```

{% hint style="success" %}
If you added everything successfully, your node will show:

**blockchain module initialized with implementation: gnosis:100**
{% endhint %}

## Step 3 - Set node ask

The default ask is set to 0.01 in the script below. Please change it to your desired ask price.&#x20;

```
npm -C /root/ot-node/current run set-ask -- --rpcEndpoint=https://astrosat-parachain-rpc.origin-trail.network/ --ask=0.01 --privateKey=$(jq -r '.modules.blockchain.implementation.otp.config.evmOperationalWalletPrivateKey' /root/ot-node/.origintrail_noderc) --hubContractAddress=0x5fA7916c48Fe6D5F1738d12Ad234b78c90B4cAdA
```

## Step 4 - Add stake

Visit the[ **staking dashboard**](https://dkg.origintrail.io/staking) and connect to your wallet using MetaMask.

Select the node you want to delegate to and click on **Delegate Stake**. Done!
