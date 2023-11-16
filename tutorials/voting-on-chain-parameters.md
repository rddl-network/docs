---
description: Voting on on-chain parameters that affect how the network functions.
---

# Voting on chain parameters

### Overview

Planetmint uses the Cosmos SDK governance module to enable stakeholders to collectively decide on important on-chain parameters and upgrades through a decentralized voting process. This documentation provides a step-by-step guide on how to participate in the voting process for chain parameters.

### Prerequisites

Before participating in the voting process, ensure that you have:

1. **Staked Tokens:** To participate in governance, you need to hold tokens staked in the network.
2. **Voting Rights:** Some networks might have additional requirements for voting, such as a minimum staking duration.

### Proposal Submission

1. **Draft a Proposal:**
   * Use the `planetmint-god tx gov draft-proposal` command to create a draft for a proposal
   * Select the transaction (e.g.: `planetmintgo.dao.MsgUpdateParams`) that shall be voted upon and set all parameters in the created draft\_proposal.json
2. **Initiate a Proposal:**
   * Proposals are submitted to suggest changes to on-chain parameters.
   * Use the `planetmint-god tx gov submit-proposal` command to initiate a proposal.
3. **Deposit Tokens:**
   * Proposers are usually required to deposit a certain number of tokens to prevent spam proposals.
   * The proposal will only move to the voting stage if the minimum deposit is reached.
   * `planetmint-god tx gov deposit 1 100stake --from validator-operator`
4. **Vetting Period:**

* Proposals go through a vetting period to allow the community to review and discuss them.
* Community members can express their opinions on the proposal during this time.

### Voting

1. **Voting Period:**
   * Once the vetting period concludes, the proposal enters the voting period.
   * Use the `planetmint-god tx gov vote` command to cast your vote.
   * `planetmint-god tx gov vote 1 yes --from validator-operator`
2. **Quorum:**
   * Some networks may require a minimum percentage of total staked tokens to participate for the vote to be valid (quorum).
3. **Threshold:**
   * Define the minimum percentage of 'Yes' votes needed for the proposal to pass.
4. **Passing or Rejection:**
   * If the proposal receives enough 'Yes' votes and meets the quorum and threshold requirements, it is accepted.
   * Otherwise, it is rejected.

### Implementation

1. **Parameter Changes:**
   * If the proposal is accepted, the on-chain parameters are updated according to the proposal's specifications.
2. **Execution:**
   * The changes are executed at the end of the voting period.

### Conclusion

Participating in the governance process allows stakeholders to actively shape the evolution of the RDDL network by voting on critical on-chain parameters. Stay informed about ongoing proposals and exercise your voting rights to contribute to the network's decentralized decision-making.

For detailed commands and examples, refer to the official Cosmos SDK documentation and CLI guides.
