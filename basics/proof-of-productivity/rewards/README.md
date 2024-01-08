# 🌈 Rewards



The final rewards of a PoP are RDDL tokens issued to a PoP-related multi-sig wallet(**PoP wallet**) on the Liquid network.

Rewarded PoP participants can claim their rewards from this wallet. Tokens to claim RDDL from the PoP-Wallet are minted once a day by a clearance process on Planetmint. The minted tokens representing claims are named **cRDDL**.

The block proposing validator verifying the ReportPoPResult message from the challenger mints **stagedCRDDL** following the [reward calculation](reward-calculation.md). The resulting stagedCRDDL tokens are converted to cRDDL by the [daily clearance process](./#daily-clearance-process).



## Daily Clearance Process

Reducing transaction fees on Liquid is the purpose of the clearance process. The clearance process is executed once a day. It contains two steps: the re-issuance and distribution of the RDDL tokens to the DAO, PoP and investor wallets.

### Re-issuance

Re-issuance is triggered periodically (once daily, configurable by the network) by the network. The block proposing validator iterates over all challenges since the last re-issuance and computes the number of tokens to be re-issued.&#x20;

The block proposer creates and broadcasts a `ReissueRDDLProposal` message. The network validates the message. The block proposer reissues the calculated tokens once the network confirms the message. Thereafter, the proposer also creates a `ReissueRDDLResult` message with the details about the reissuance. &#x20;

### Distribution



##
