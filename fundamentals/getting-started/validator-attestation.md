# 👾 Validator Attestation

Validators are attested like machines are attested. Some of the field however are predfined and the initial asset definition struct looks as follows:

````json
```json
{
    "name": "RDDL Validator ID",
    "ticker": "RDDLV ID",
    "amount": 1,
    "precision": 8,
    "public_url": "https://rddl.io",
    "reissue": True,
    "cid": "CID string",
    "machine id": "machine identity of the secure element",
    "issuer_liquid": "m/44/LBTC/0/0/0",
    "issuer_planetmint": "m/44/PLMNT/0/0/0",
}
```
````

The metadata CID string comprises of the following tuple

````json
```json
{
    "Device": "...",
    "GPS": "...",
    "Asset Definition": "..."
}
````

With the following specific definitions

````
{ 
    "Device": {
      "DMIName": "System Information",
      "DMISize": 27,
      "DMIType": 1,
      "Family": "QN",
      "Manufacturer": "Intel(R) Client Systems",
      "Product Name": "NUC9VXQNX",
      "SKU Number": "BKNUC9VXQNX",
      "Serial Number": "JRQN027302GK",
      "UUID": "ddadbe4e-ba9d-11ea-9e72-9e7acb4ae300",
      "Version": "K47173-402",
      "Wake-up Type": "Power Switch"
    },
    "GPS": {
      "data": {
        "geo": {
          "asn": 8412,
          "city": "Vienna",
          "continent_code": "EU",
          "continent_name": "Europe",
          "country_code": "AT",
          "country_name": "Austria",
          "datetime": "2023-01-20 10:12:18",
          "host": "node1-rddl-testnet.twilightparadox.com",
          "ip": "84.112.103.218",
          "isp": "T-Mobile Austria GmbH",
          "latitude": 48.1968,
          "longitude": 16.3191,
          "metro_code": null,
          "postal_code": "1150",
          "rdns": "84-112-103-218.cable.dynamic.surfer.at",
          "region_code": "9",
          "region_name": "Vienna",
          "timezone": "Europe/Vienna"
        }
      },
    "Asset Definition": {
            "VersionControl": {"PASStandardVersionNumber": "PAS19668:2020", "SecurityTokenFileVersionNumber": "1.0.0"},
            "SecurityTokenDataStore": "https://linktoyoursecuritytokenwebsite.com/pasdata/current_version.json",
            "SecurityTokenLocation": {
                "STBlockchain": [
                    {
                        "STBlockchainName": "Liquid",
                        "STBlockchainInformation": "https://blockstream.com/liquid/",
                        "STTokenizationSolution": ["RDDL Asset Registry"],
                        "STBlockchainUniqueAssetIdentifier": "a28d04f3e243a9a187f4a8b797be2f19a9c01b6ef4e1d65bfb6abbd6a2042097",
                        "ProgrammationOfSecurityToken": "ProgramCryptoConditions",
                        "SecurityTokenTransferVerificationLogic": "VerificationPreTransfer",
                        "SecurityProcedures": ["CapableFreezeAccount", "CapableFreezeST"],
                    }
                ],
                "STIdentificationNumber": "Asset identification according to BS ISO 6166",
            },
            "SecurityTokenClassification": {"IdentificationOfST": {"CFICodeVersion": "1.0", "CFICodeValue": "CFI001"}},
            "InformationDisclosures": {
                "IssuerDisclosures": {
                    "IssuerName": "RDDL Foundation",
                    "IssuerIndustryClassification": "604885180106232618",
                    "IssuerJurisdiction": "LI",
                    "IssuerContactDetails": "c/o at4you AG, Rhigass 1, 9487 Gamprin-Bendern, Liechtenstein",
                    "IssuerNewsFeed": ["https://twitter.com/RDDLNetwork"],
                    "IssuerIncorporationDocuments": "https://rddl.io/incorporation.doc",
                    "IssuerOfferingDocuments": "https://rddl.io/offering.doc",
                    "IssuerAccountInformation": "https://rddl.io/accounting.doc",
                },
                "IssuerAssetDisclosures": {
                    "STTotalSupply": 1,
                    "STFractionalization": True,
                    "STAssetInvestmentProfile": "https://rddl.io/InvestmentProfile",
                    "STMarkets": ["https://rddl.io"],
                    "STPriceDetermination": "STMarketPrice",
                    "AssetBacking": "AssetBacked",
                    "AssetCustodianship": "AssetCustodied",
                    "AssetCustodian": "RDDL Foundation",
                },
            },
            "EligibleInvestorClassification": {"EligibleInvestorCountriesList": [], "RestrictedCountries": ["LI"]},
            "SecurityTokenTechnicalProperties": {
                "IncomeProperties": "IncomeDifferentAddress",
                "VotingProperties": "NoVoting",
                "DelegateRegister": "DelegateTA",
            },
            "KYCAMLRequirements": {"IdentityDocuments": "Passport", "ComplianceRequirements": ""},
        }
}
```
````
