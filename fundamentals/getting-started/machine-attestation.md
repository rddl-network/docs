# 🧑 Machine Attestation

Attestation of the machine identity (only possible with a challenge valid response of an pre-attested machine (Testnet ) ([https://github.com/RiddleAndCode/0x21e8/issues/12](https://github.com/RiddleAndCode/0x21e8/issues/12))

1. Workflow:
   1. metadata attestation with IPLD \
      ![](<../../.gitbook/assets/Untitled (4).png>)
   2. Attestation of the machine on Liquid & Planetmint: creation of the NFT on planemtint and issuing machine tokens on Liquid ![](<../../.gitbook/assets/Untitled (5).png>)
2. Attestation on Liquid
   1. Name of the asset (e.g. RDDL-Token)
   2. Ticker symbol (e.g. RDDL)
   3. Reference web-domain of the machine owner (well-known entry that works like a soft-KYC)
   4. asset amount
   5. re-issuance : yes / no
   6. precision: natural numbers or decimals (0 means 8 post decimal places, 8 means natural numbers, 7 means 1.0 …. 1.9)
   7. IPLD hash reference (if Planetmint attestation is done first)
   8. metadata on plntmnt as IPLD hash
3. Attestation on planetmint
   1. Liquid hash reference (if Liquid attestation is done first)
   2. IPLD to metadata
   3. machine ID (public key of the SE050)
   4. primary liquid public key : m/44/LBTC/0/0/0
   5. primary planetmint public key: m/44/PLMNT/0/0/0
