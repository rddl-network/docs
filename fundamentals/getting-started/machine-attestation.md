---
description: >-
  Attestation of the machine identity (only possible with a challenge valid
  response of an pre-attested machine (Testnet )
  (https://github.com/RiddleAndCode/0x21e8/issues/12)
---

# 🧑 Machine Attestation

### Workflows

**Metadata attestation** by [CIDs](https://github.com/multiformats/cid) based on [IPLD](https://ipld.io/)

```bash
rddl-client attest-data --help
                                                                                                                                                                                                              
 Usage: rddl-client attest-data [OPTIONS] DATA                                                                                                                                                                
                                                                                                                                                                                                              
 This method stores the given JSON data on the configured storage solution and notarizes the resulting CID on RDDL, thereafter.                                                                               
                                                                                                                                                                                                              
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ *    data      TEXT  A dcit object in string representation that is to be stored on IPFS and attested on RDDL. [default: None] [required]                                                                  │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --encrypt                                                                                                                                                                                                  │
│ --help             Show this message and exit.                                                                                                                                                             │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```

**Attestation of the machine** on Liquid & Planetmint: creation of the NFT on planetmint and issuing machine tokens on Liquid&#x20;

```bash
rddl-client attest-machine --help
                                                                                                                                                                                                              
 Usage: rddl-client attest-machine [OPTIONS] NAME TICKER AMOUNT PRECISION                                                                                                                                     
                                   PUBLIC_URL [CID]                                                                                                                                                           
                                                                                                                                                                                                              
 This method issues the requested machine tokens for the machine on RDDL and notarizes the machine and the issued tokens.                                                                                     
                                                                                                                                                                                                              
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ *    name            TEXT     The name of the machine token that will be issued. [default: None] [required]                                                                                                │
│ *    ticker          TEXT     The ticker of the machine token that will be issued. [default: None] [required]                                                                                              │
│ *    amount          INTEGER  The number of tokens that are to be issued. [default: None] [required]                                                                                                       │
│ *    precision       INTEGER  The precision of the token. [default: None] [required]                                                                                                                       │
│ *    public_url      TEXT     The legal entity that this machine and token are associated with. [default: None] [required]                                                                                 │
│      cid             [CID]    The CID of the token details. This needs to created and handled before calling this method. In case this is not defined, the IP geolocation and machine data as well as the  │
│                               default asset definition are created.                                                                                                                                        │
│                               [default: None]                                                                                                                                                              │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --reissue    --no-reissue      [default: reissue]                                                                                                                                                          │
│ --help                         Show this message and exit.                                                                                                                                                 │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```

The attestation of machines implicitly attests the following data on Liquid and RDDLs planetmint

1. Attestation on Liquid
   1. Name of the asset (e.g. RDDL-Token)
   2. Ticker symbol (e.g. RDDL)
   3. Reference web domain of the machine owner (a well-known entry that works like a soft KYC)
   4. asset amount
   5. re-issuance: yes/no
   6. precision: natural numbers or decimals (0 means eight post decimal places, 8 means natural numbers, 7 means 1.0 …. 1.9)
   7. IPLD hash reference (if Planetmint attestation is done first)
   8. metadata on planetmint as CID
2. Attestation on planetmint
   1. Liquid hash reference (if Liquid attestation is done first)
   2. IPLD to metadata
   3. machine ID (public key of the SE050)
   4. primary liquid public key: m/44/LBTC/0/0/0
   5. primary planetmint public key: m/44/PLMNT/0/0/0
