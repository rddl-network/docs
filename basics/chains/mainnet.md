# 🕸️ Mainnet

The mainnet consists of several components, but most importantly it runs a version of [planetmint-go](https://github.com/planetmint/planetmint-go) and a [liquid](https://github.com/ElementsProject/elements) node.

## Planetmint Configuration

**ChainID:** planetmint-mainnet-1

**Denomination:** PLMNT

**Genesis:** [genesis.json](planetmint-mainnet-1-genesis.json)

## Links

| Name     | URL                      |
| -------- | ------------------------ |
| explorer | https://explorer.rddl.io |
| api      | https://api.rddl.io      |
| rpc      | https://rpc.rddl.io      |
| ta       | https://ta.rddl.io       |

## Infrastructure

The infrastructure runs on AWS and is managed by [Pulumi](https://github.com/rddl-network/pulumi-aws) and [Ansible](https://github.com/rddl-network/ansible).

| Name                           | Instance Type | URL                             |
| ------------------------------ | ------------- | ------------------------------- |
| planetmint-go-mainnet-1        | t3.medium     | planetmint-go-mainnet-1.rddl.io |
| planetmint-go-mainnet-2        | t3.medium     | planetmint-go-mainnet-2.rddl.io |
| planetmint-go-mainnet-3        | t3.medium     | planetmint-go-mainnet-3.rddl.io |
| planetmint-go-mainnet-explorer | t3.medium     | explorer.rddl.io                |

## Configuration

One can find the configuration at https://github.com/rddl-network/ansible/tree/main/templates/planetmint-go/.
