---
description: Is the process that gives an identifier/identity/secret to a machine.
---

# 📝 Machine Provisioning

A user can restore a previous seed by initializing the service with a  **given** mnemonic phrase ([https://github.com/rddl-network/rddl-client](https://github.com/rddl-network/rddl-client)), the recover-seed.

```bash
rddl-client recover-seed --help
                                                                                                                                                                                                              
 Usage: rddl-client recover-seed [OPTIONS] MNEMONIC_PHRASE                                                                                                                                                    
                                                                                                                                                                                                              
 Recovers a seed from the menmonic phrase passed to the method (12 or 24 words). The length of the resulting mnemonic phrase implicitly defines the length of the seed.                                       
                                                                                                                                                                                                              
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ *    mnemonic_phrase      TEXT  The mnemonic phrase, a space seperated list of 12 or 24 words [default: None] [required]                                                                                   │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --help          Show this message and exit.                                                                                                                                                                │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯


```

The second option is to request the creation of a **new** mnemonic phrase ([https://github.com/rddl-network/rddl-client](https://github.com/rddl-network/rddl-client)) create-seed 24\


```bash
rddl-client create-seed --help
                                                                                                                                                                                                              
 Usage: rddl-client create-seed [OPTIONS] [WORDS]                                                                                                                                                             
                                                                                                                                                                                                              
 Creates a seed based on true randomness and provices a mnemonic phrase (12 or 24 words) as a backup of the generated seed. The length of the resulting mnemonic phrase implicitly defines the length of the  
 seed.                                                                                                                                                                                                        
                                                                                                                                                                                                              
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│   words      [WORDS]  The number of words (12 or 24) that the mnemonic phrase to be derived should contain. [default: 24]                                                                                  │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --help          Show this message and exit.                                                                                                                                                                │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯


```

The user has to define the security and therewith the length of the of the recovery phrase. The mnemonic phrase can be 12 or 24 words in length.

Now, the following aspects will be issued:

1. create mnemonic phrase and displays the phrase
2. The user has to write down the mnemonic phrase
3. derive the seed of the mnemonic phrase
4. write the seed to the SE050 / CM4 module \
