# 🔢 Reward Calculation

The network waits for the challenger to respond with the ReportPopResult for two PoP epochs (2 times 2 minutes). The rewards for the PoP are then calculated depending on the outcome of the PoP.



```mermaid
flowchart TD
    X[After sending out the InitPoP]--> |Enter waiting state| Y
    Y{Waiting for PoP Result}-->|No PoP Result received within the duration of 2 PoP epochs| J
    Y-->|On PoP Result for the acting Validator| B{Is the message's creator the challenger?}
    B -->|Created by Challenger| C{\n Has the challenge been solved?}
    C -->|Challenge solved!| D[mint Staged RDDLclaims: 2% challenger,  6% challengee]

    B -->|Not created by the challenger| J[8% to the DAO due to no trust in the PoP result.]
    C -->|Challenge not solved| E[mint Staged RDDLclaims: 2% challenger,  6% DAO]

```

