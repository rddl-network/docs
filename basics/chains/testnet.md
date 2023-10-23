# Testnet

The testnet consists of several components, but most importantly it runs a version of [planetmint-go](https://github.com/planetmint/planetmint-go) and a [liquid](https://github.com/ElementsProject/elements) node.

## Chain ID

**planetmint-testnet-1**

## Links

| Name | URL |
|---|---|
| explorer | https://testnet-explorer.rddl.io |
| api | https://testnet-api.rddl.io |
| rpc | https://testnet-rpc.rddl.io |
| ta | https://testnet-ta.rddl.io |
| faucet | https://testnet-faucet.rddl.io |

## Infrastructure

The infrastructure runs on AWS and is managed by [Pulumi](https://github.com/rddl-network/pulumi-aws) and [Ansible](https://github.com/rddl-network/ansible).

| Name | Instance Type | URL |
|---|---|---|
| planetmint-go-testnet-1 | t3.medium | planetmint-go-testnet-1.rddl.io |
| planetmint-go-testnet-2 | t3.medium | planetmint-go-testnet-2.rddl.io |
| planetmint-go-testnet-3 | t3.medium | planetmint-go-testnet-3.rddl.io |
| planetmint-go-testnet-explorer | t3.medium | testnet-explorer.rddl.io |

## Configuration

One can find the configuration at https://github.com/rddl-network/ansible/tree/main/templates/planetmint-go/.
