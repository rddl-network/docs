---
description: >-
  PoP attests to two facts. That the machine actively consumed or produced
  energy and that the machine can prove data availability and integrity as
  stated by its CID notarization.
---

# ⁉ Challenge-Response

At the end of an epoch (2 min), the proposing Validator initiates the PoP-related challenge response by sending MQTT messages to the challenger and the challengee (see [Actor Selection ](actor-selection.md)paragraph).

The initialized challenge-response process is described below:

1. Challenger and challengee request the details of the PoP by calling [/planetmint/dao/challenge/{height}](https://testnet-api.rddl.io/#/Query/PlanetmintgoDaoGetChallenge).
2. The challenger selects a random `CID` from a list of CIDs for a certain period of time provided by calling [/planetmint/asset/address/{address}/{lookupPeriodInMin}](https://testnet-api.rddl.io/#/Query/PlanetmintgoAssetGetCIDsByAddress).
3. The challenger subscribes to the `PoPChallengeResult-`topic of the challangee (`stat/<challangee-address>/POPCHALLENGERESULT`).
4. The challenger sends the `cmnd/<challangee-address>/PoPChallenge <CID>` command to the challengee.
5. The challengee looks up the corresponding CID data and transfers it to the challenger via the `POPCHALLENGERESULT`command.
6. The challenger receives the data via the subscribed topic and computes the `CID'` of the provided content.&#x20;
7. The challenger notarizes a ReportPopResult message with `Success = true` if the computed `CID'` equals the requested `CID` and `Success = false`, otherwise.
8. The challenger unsubscribes from `stat/<challangee-address>/POPCHALLENGERESULT`.





```mermaid
sequenceDiagram
participant Validator
participant Challenger
participant Challengee
Participant Planetmint-Node

Validator->>Challenger: M2M: request to perform the challenge (PopInit <block height>)
Validator->>Challengee: M2M: request to perform the challenge (PopInit <block height>)

Challenger->>Planetmint-Node: lookup PoPInit <block height> to get the challengee and the block-height
Challengee->>Planetmint-Node: lookup PoPInit <block height> to get the challengeer and the block-height



loop Select CID
Challenger->>Planetmint-Node: request notarized CIDs of the Challengee for last month
Planetmint-Node->>Challenger: return notarized CIDs TXs of the challengee
Challenger->>Challenger: select a random CID
end 

loop Challenge CID
Challenger->>Challenger: Subscribe to topic "stat/<challangee-address>/POPCHALLENGERESULT"
Challenger->>Challengee: send command "cmnd/<challangee-address>/PoPChallenge <CID>"
Challengee->>Challengee: lookup CID content from FS
Challengee->>Challengee: respond via stat/<challangee-address>/POPCHALLENGERESULT" CONTENT and requested CID
Challenger->>Challenger: compute CID` create_cid(CONTENT_I) and compare result to CID
Challenger->>Challenger: unsubscribe from "stat/<challangee-address>/POPCHALLENGERESULT"
end

Challenger->>Challenger: Create PoP Result: ReportPopResult with the challenge details.
Challenger->>Challenger: set Challenge.Success = (CID` == CID)
Challenger->>Planetmint-Node: notarize and broadcast PoP Result

```
