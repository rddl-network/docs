# RDDL on Liquid

## Token Lifecycle

**Issuance**: Initially, 998.69 RDDL were issued on Liquid.&#x20;

**Re-issuance**: Planetmint consensus triggers a re-issuance of RDDL tokens every 2 minutes after the **Proof of Productivity**. The re-issuance is defined as follows:

* First 4 Years: 998.69 tokens every 2 minutes
* Second 4 Years: 499.34 tokens every 2 minutes
* Third 4 Years: 249.67 tokens every 2 minutes
* Fourth 4 Years: 124.83 tokens every 2 minutes
* Fifth 4 Years: 62.42 tokens every 2 minutes

**Distribution**: Issued and re-issued tokens are distributed to&#x20;

* DAO 61%
* Investors 31%
* PoP escrow 8%

**Reconciliation**: Reissuance and distribution are triggered every 24 hours to reduce Liquid's economic footprint/costs.

## Liquid Wallets

RDDL Network-operated Liquid wallets are protected and only accessible via a **2-out-of-3** or **3-out-of-5** quorum. All wallets are only opened and accessed for transferring funds.

### Re-/Issuance wallet

A quorum protects the wallet issuing and re-issuing of the RDDL tokens. The wallet is only opened and accessed during the re-issuance and distribution phase.

### PoP escrow

All PoP rewards are distributed to the PoP escrow account managed by the validators.

Machines and operators can claim their PoP rewards by issuing a PopClaim message on the Planetmint network. Rewards will then be distributed to the specified address on Liquid.

### DAO escrow

The DAO escrow converts 10% of all incoming re-issued tokens into PLMNTs and distributes them evenly to the validators to support their operations.

### RDDL2PLMNT escrow

The RDDL2PLMNT service maintains the escrow mints **planets** (PLMNT tokens) for the incoming amount of RDDL tokens. The initial conversion rate is equal to **1 PLMNT = 0.04 RDDL.**
