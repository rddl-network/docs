# 💳 Micro-Investment



RDDL Network enables machine operators to issue dedicated [asset tokens](../fundamentals/tokens/asset-tokens.md) during the [machine attestation](../fundamentals/getting-started/machine-attestation.md).

The asset tokens are managed via the [issuer wallet](../wallet-types.md) by the machine operator of the attestation. The asset tokens can be fractionalized and transferred to other wallets or beneficiaries via the 0x21e8 service that manages the issuer wallet or tools connected to the service.&#x20;

Machine owners can now build applications containing policies, contracts and legal frameworks around the asset token that incentivize micro-investments into their assets.

Micro-Investors could be&#x20;

* indirectly participate in the PoP returns
* utilized their investment/asset tokens to swap them into products of the machine
* rewarded for staking their asset tokens

The actual implementation and realization are up to the machine operator.

[RDDL-client](https://github.com/rddl-network/rddl-client) enables machine operators to trade the assets/tokens of the machine wallet. The client needs to be configured to connect to the machine [0x21e8 service](https://github.com/rddl-network/0x21e8) and can start trading the tokens from there on.&#x20;

```bash
rddl-client transfer-token --help
                                                                                                                                                                                                              
 Usage: rddl-client transfer-token [OPTIONS] TOKEN_ID OUTPUT_ID RECIPIENT                                                                                                                                     
                                                                                                                                                                                                              
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ *    token_id       TEXT     The transaction that is to be transferred. [default: None] [required]                                                                                                         │
│ *    output_id      INTEGER  The output of the transaction that is to be transferred. [default: None] [required]                                                                                           │
│ *    recipient      TEXT     The address of the recipient to receive the transferred tokens. [default: None] [required]                                                                                    │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│    --nw-symbol                                                                                TEXT     The SLIP-44 network symbol the transaction is created for.                                          │
│ *  --nw-id                                                                                    INTEGER  The SLIP-44 network id the transaction is created for. [default: None] [required]                   │
│    --account                                                                                  INTEGER  The account ID of the BIP44 HD path. [default: 0]                                                   │
│    --change                                                                                   INTEGER  The change type of the BIP44 HD path. [default: 0]                                                  │
│    --index                                                                                    INTEGER  The index of the BIP44 HD path. [default: 0]                                                        │
│    --amount                                                                                   FLOAT    The amount of tokens being send. This can only be an integer compatible value for Planetmint.       │
│                                                                                                        [default: 1.0]                                                                                      │
│    --confidential    --no-confidential, this is only supported on Liquid (Not Planetmint).             [default: no-confidential, this is only supported on Liquid (Not Planetmint).]                      │
│    --help                                                                                              Show this message and exit.                                                                         │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯


```

