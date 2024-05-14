---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ⛓️ Networks

The following public networks are currently maintained and available:

## Configuration

One can find the configuration in the GitHub[ ansible repository](https://github.com/rddl-network/ansible/tree/main/templates/planetmint-go/).

|                  | Mainnet                                                  | Testnet                                                  |
| ---------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| **ChainID**      | planetmint-mainnet-1                                     | planetmint-testnet-1                                     |
| **Denomination** | PLMNT                                                    | PLMNT                                                    |
| **Genesis**      | [genesis.json](chains/planetmint-mainnet-1-genesis.json) | [genesis.json](chains/planetmint-testnet-1-genesis.json) |



## Links

<table data-full-width="false"><thead><tr><th width="263">Name</th><th width="218">Mainnet</th><th>Testnet</th></tr></thead><tbody><tr><td>Explorer</td><td>https://explorer.rddl.io</td><td>https://testnet-explorer.rddl.io</td></tr><tr><td>API (Planetmint)</td><td>https://api.rddl.io</td><td>https://testnet-api.rddl.io</td></tr><tr><td>RPC (tendermint)</td><td>https://rpc.rddl.io</td><td>https://testnet-rpc.rddl.io</td></tr><tr><td>Trust Anchor registration</td><td>https://ta.rddl.io</td><td>https://testnet-ta.rddl.io</td></tr><tr><td>Faucet</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td><td>https://testnet-faucet.rddl.io</td></tr><tr><td>rddl2plmnt</td><td>https://r2p.rddl.io</td><td>https://testnet-r2p.rddl.io</td></tr><tr><td>rddl claims</td><td>https://p2r.rddl.io</td><td>https://testnet-p2r.rddl.io</td></tr><tr><td>Machine 2 Machine (MQTT) (deprecated)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td><td>mqtt://testnet-mqtt.rddl.io:1885 </td></tr><tr><td>Machine 2 Machine (MQTT+TLS)</td><td>mqtt://mqtt.rddl.io:1884</td><td>mqtt://testnet-mqtt.rddl.io:1886</td></tr></tbody></table>

## Machine 2 Machine Network

RDDL Network currently uses MQTT as the machine-to-machine network. The service will be extended so that machines can authenticate via a JWT token related to their private/public key on Planetmint.&#x20;

However, at this point, the following user/password pairs can be used to access the services on testnet and mainnet&#x20;

<table><thead><tr><th width="181">Network</th><th width="158">User</th><th>Password</th></tr></thead><tbody><tr><td>testnet</td><td>rddl-tasmota</td><td>bE91dLR49FmsTtR2xbFCJfmgaGwTqeZJ</td></tr><tr><td>mainnet</td><td>rddl-tasmota</td><td>Xs0liJviALEJLWgHJ3vI4MbYHqahG0sP</td></tr></tbody></table>



## Infrastructure

The infrastructure runs on AWS and is managed by [Pulumi](https://github.com/rddl-network/pulumi-aws) and [Ansible](https://github.com/rddl-network/ansible).

### Mainnet

<table><thead><tr><th>Name</th><th width="157.33333333333331">Instance Type</th><th>URL</th></tr></thead><tbody><tr><td>planetmint-go-mainnet-1</td><td>t3.large</td><td>planetmint-go-mainnet-1.rddl.io</td></tr><tr><td>planetmint-go-mainnet-2</td><td>t3.large</td><td>planetmint-go-mainnet-2.rddl.io</td></tr><tr><td>planetmint-go-mainnet-3</td><td>t3.large</td><td>planetmint-go-mainnet-3.rddl.io</td></tr><tr><td>planetmint-go-mainnet-explorer</td><td>t3.large</td><td>explorer.rddl.io</td></tr></tbody></table>

### Testnet

<table><thead><tr><th>Name</th><th width="156.33333333333331">Instance Type</th><th>URL</th></tr></thead><tbody><tr><td>planetmint-go-testnet-1</td><td>t3.medium</td><td>planetmint-go-testnet-1.rddl.io</td></tr><tr><td>planetmint-go-testnet-2</td><td>t3.medium</td><td>planetmint-go-testnet-2.rddl.io</td></tr><tr><td>planetmint-go-testnet-3</td><td>t3.medium</td><td>planetmint-go-testnet-3.rddl.io</td></tr><tr><td>planetmint-go-testnet-explorer</td><td>t3.medium</td><td>testnet-explorer.rddl.io</td></tr></tbody></table>

