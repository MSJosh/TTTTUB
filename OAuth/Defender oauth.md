**Microsoft Entra ID Protection**
- Entra ID Identity Protection detects the described threats with the following alerts:

    - Anomalous Token
    - Unfamiliar sign-in properties
    - Anonymous IP address
    - Verified threat actor IP

**Microsoft Defender for Cloud Apps**
- Using Microsoft Defender for Cloud Apps connectors especially for Azure, Microsoft 365 Defender raises the following alerts:

    - Activity from anonymous IP address

**App Governance**
- App governance is an add-on to Microsoft Defender for Cloud Apps, which can detect malicious OAuth applications that make sensitive Exchange Online administrative activities along with other threat detection alerts. Activity related to this campaign triggers the following alert:

    - Entra Line-of-Business app initiating an anomalous spike in virtual machine creation
    - OAuth app with high scope privileges in Microsoft Graph was observed initiating virtual machine creation


**Defender XDR**
- Microsoft 365 Defender detects threat components associated with the following activities:

    - Suspicious secret addition to OAuth app followed by creation of Azure virtual machines
    - Risky user created or updated a suspicious app previously seen creating bulk VMs

**Microsoft Defender for Cloud**
- Microsoft Defender for Cloud detects threat components associated with the activities outlined in this article with the following alerts:

    - Azure Resource Manager operation from suspicious proxy IP address
    - Crypto-mining activity
    - Digital currency mining activity
    - Suspicious Azure role assignment detected.
    - Suspicious creation of compute resources detected
    - Suspicious invocation of a high-risk ‘Execution’ operation by a service principal detected
    - Suspicious invocation of a high-risk ‘Execution’ operation detected
    - Suspicious invocation of a high-risk ‘Impact’ operation by a service principal detected
