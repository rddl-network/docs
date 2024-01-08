# ⌚ Clearance Process

Reducing transaction fees on Liquid is the purpose of the clearance process. The clearance process is executed once a day. It contains two steps: the re-issuance and distribution of the RDDL tokens to the DAO, PoP and investor wallets.

### Re-issuance

Re-issuance is triggered periodically (once daily, configurable by the network) by the network. The block proposing validator iterates over all challenges since the last re-issuance and computes the number of tokens to be re-issued.&#x20;

The block proposer creates and broadcasts a `ReissueRDDLProposal` message. The network validates the message. The block proposer reissues the calculated tokens once the network confirms the message. Thereafter, the proposer also creates a `ReissueRDDLResult` message with the details about the reissuance. &#x20;

### Distribution

The distribution of the re-issued tokens is set to 30 minutes (15 epochs) after the re-issuance. The block proposer initializes the distribution by issuing the `DistributionRequest` message. The network validates the message. The block proposer distributes the tokens following the proposal after the network confirms the message. Thereafter, the proposer creates a DistributionResult message with the corresponding transaction IDs and broadcasts the message to the network.
