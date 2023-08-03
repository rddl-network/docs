# 🪙 Tokens

### Token Definitions

1. [**RDDL**](rddl-token.md) is the **registry token**. Some refer to this as the ‘incentive’ token.
2. [**Machine Identity Token**](../../basics/tokens/machine-identity-token.md) is issued on planetmint during the machine attestation process. The extended public key of the machine is notarized. Another type is also added.
3. [**RDDL Purpose Tokens**](../../basics/tokens/rddl-purpose-tokens.md) are issued on Liquid Network by 3rd parties (economic actors) and used to interact economically with machines.
4. [**CID Assets**](../../basics/tokens/cid-assets.md) are issued on planetmint,
   * are non-fungible,
   * and contain machine-generated metadata, per the machine owner's discretion.
5. Tokens from other networks can be wrapped as Liquid Tokens. They are called [**wrapped tokens**](wrapped-tokens.md)**.**
   * example: Ocean ERC (ETH) token 1:1 wrapped on Liquid via ‘escrow’ account



### Tokens & Layers

| Token                   | Layer              |
| ----------------------- | ------------------ |
| RDDL                    | Layer 2 Liquid     |
| Machine Identity Tokens | Layer 2 Liquid     |
| RDDL Purpose Tokens     | Layer 2 Liquid     |
| CID Assets              | Layer 1 Planetmint |
| Wrapped Tokens          | Layer 2 Liquid     |

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
