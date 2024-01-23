# 🌈 Rewards

The following paragraphs give an overview of how rewards are created and managed. The following stages are processed until someone can access their RDDL rewards:

1. [Reward Calculation](./)
2. [Clearance Process](clearance-process.md): re-issuance & distribution

## Staging the Rewards

RDDL tokens are issued as the final rewards of a PoP to a PoP-related multi-sig wallet(**PoP wallet**) on the Liquid network.

Rewarded PoP participants can claim their rewards from this wallet. Tokens to claim RDDL from the PoP-Wallet are minted once a day by a clearance process on Planetmint. The minted tokens representing claims are named **cRDDL** (claimable RDDL).

The block proposing validator verifying the ReportPoPResult message from the challenger mints **stagedCRDDL** following the [reward calculation](reward-calculation.md). The resulting stagedCRDDL tokens are converted to cRDDL by the [clearance process](./#daily-clearance-process).

## Claiming RDDLS

Details are to be defined. The claiming of RDDL will be issued by a Planetmint message. That message will burn cRDDL and transfer RDDL tokens from the PoP wallet to the specified Liquid address.

{% hint style="info" %}
More details will follow soon.
{% endhint %}

##
