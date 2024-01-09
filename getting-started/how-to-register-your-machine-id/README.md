# ❓ Is my Hardware Supported?

Registering your Machine ID is a crucial step in onboarding your machine to the RDDL Network. The process varies depending on your machine type. Below, you'll find a flowchart that outlines the steps based on whether your hardware is RDDL certified, officially supported, or currently unsupported.

```mermaid fullWidth="true"
flowchart TD
    A[Hardware]-->B
    B{Is the HW officially supported} --> |officially supported| C
    C{Does it come with a unique\npreregistered Public Key}-->|yes| D
    D(Use your HW and attest the machine)
    C-->|no| E
    E(Download unique Firmware)-->|Flash Firmware| D
    B-->|not officially supported| J
    F(Integrate libRDDL & Implement Testnet compatibility)--> |pass the HW approval and verification process| D
		F--> G
    G(create REP-9 PR)--> |apply for Certified 3rd Party OEM vendor| I
    I(The process to become a Certified RDDL HW OEM vendor)
		J{Is it a ESP32/C3 Device?}-->|yes| E
		J{Is it a ESP32/C3 Device?}-->|no| F
```

**Flowchart Explanation:**

1. **RDDL Certified Hardware:**
   * As soon as your hardware is RDDL certified, it is officially supported.
   * Check if it comes with a unique preregistered Public Key.
   * If yes, you can directly use your hardware and proceed to attest the machine.
2. **Supported Hardware:**
   * If your hardware is officially supported but **DOES NOT** come with a unique preregistered Public Key:
     * Download the unique firmware provided.
     * Flash the firmware onto your hardware.
     * Proceed to attest your machine.
   * If your hardware is officially supported and **DOES** come with a unique preregistered Public Key:
     * &#x20;you can Proceed to attest your machine.
3. **Unsupported Hardware:**
   * If your hardware is ESP32/C3, follow the flow to download unique firmware and attest.
   * If your hardware is **NOT** a ESP32/C3 device:
     * Integrate libRDDL and implement Testnet compatibility.
     * Pass the [hardware approval and verification process](rddl-network-hw-approval-process.md).
     * Create [REP-9](https://github.com/rddl-network/REPs) Pull Request.
     * Apply to become a Certified 3rd Party OEM vendor for RDDL.

By following the steps in this flowchart, you can successfully register your Machine ID based on your hardware type. If you encounter any challenges or have questions, feel free to refer to additional resources or contact our support team for assistance. Happy onboarding!
