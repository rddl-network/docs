# 🏁 Proof of Productivity

## Overview

The Proof of Productivity is periodically executed, and its result (negative or positive) leads to and influences the reward distribution based on a multi-sig token re-issuance process on liquid.

{% hint style="info" %}
Under the assumption that a single point of notarized data (CID) exposes and thus discloses no relevant information, PoP can be viewed and interpreted as a multi-round zero-knowledge proof.&#x20;
{% endhint %}

## Stages of Pop

The following stages of PoP exist:

1. [**Actor Selection**](actor-selection.md)**:** The block-creating validator selects the PoP actors and initiates the PoP with the selected actors
2. [**Challenge-Response**](challenge-response.md): The challenger and challengee execute/perform the PoP.
3. [**Rewards**](rewards/): The validators evaluate the notarized PoP Result and issue RDDL tokens as rewards.

{% hint style="info" %}
The current implementation is based on MQTT. The goal is to switch XMPP to guarantee a privacy-preserving PoP.
{% endhint %}
