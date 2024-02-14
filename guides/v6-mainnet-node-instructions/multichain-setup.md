---
description: 'Last updated: 2024-02-06'
---

# Multichain setup

#### The guide below is for running a node on both NeuroWebAI and Gnosis chain.&#x20;

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

## Step 1 - Preparations

Begin by obtaining xDAI for operations on Gnosis chain through their [f**aucet**](https://www.gnosisfaucet.com/).&#x20;

If you require more xDAI, you can buy DAI on [**Uniswap**](https://app.uniswap.org/swap) or any exchange and use the [**DAI bridge**](https://bridge.gnosischain.com/) to get xDAI.&#x20;

Since Gnosis is EVM compatible, you can use your Ethereum wallet on MetaMask or Ledger for all operations on the chain.&#x20;

If you want to delegate to your own node, bridge your ERC-20 TRAC from Ethereum to Gnosis by using the [**Omnibridge**](https://omnibridge.gnosischain.com/bridge)**.**

{% hint style="info" %}
A node can be fully operational with delegated stake only as long as the total stake amount is 50k TRAC or above.
{% endhint %}

Now, you need an [**Archival RPC Endpoint** ](https://docs.gnosischain.com/tools/rpc/)to communicate with the Gnosis chain. Note that not all providers provide archival endpoints. You will need to sign up through their links and get an Archival RPC Endpoint.&#x20;

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
  "config": {
    "rpcEndpoints": [
      "https://<desired_rpc_endpoint>"
      ],
    "gasPriceOracleLink": "https://blockscout.chiadochain.net/api/v1/gas-price-oracle",
    "sharesTokenSymbol": "shares_token_symbol",
    "sharesTokenName": "shares_token_name",
    "operationalWallets": [
      {
        "evmAddress": "0x0bf...",
        "privateKey": "0x1e3..."
      }
    ],
    "evmManagementWalletPublicKey": "0xd09..."
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
            "sharesTokenSymbol": "symbol...",
            "sharesTokenName": "name...",
            "operationalWallets": [
              {
                "evmAddress": "0x0bf...",
                "privateKey": "0x1e3..."
              }
            ],
            "evmManagementWalletPublicKey": "0xd09..."
          }
        },
        "gnosis:100": {
          "enabled": true,
          "config": {
            "rpcEndpoints": [
              "https://<desired_rpc_endpoint>"
            ],
            "gasPriceOracleLink": "https://blockscout.chiadochain.net/api/v1/gas-price-oracle",
            "sharesTokenSymbol": "symbol...",
            "sharesTokenName": "name...",
            "operationalWallets": [
              {
                "evmAddress": "0x0bf...",
                "privateKey": "0x1e3..."
              }
            ],
            "evmManagementWalletPublicKey": "0xd09..."
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

Visit [**Houston**](https://houston.origintrail.io/login) **and connect your admin wallet. Head to Service Tokenomics and follow the on screen instructions to set up node operator fee, node ask and node stake!**

**You can then visit the**[ **staking dashboard**](https://dkg.origintrail.io/staking) to find your node.

Done!
