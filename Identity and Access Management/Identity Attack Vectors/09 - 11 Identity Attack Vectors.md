## Indicators of Compromise
Four aspects that can create an IoC:
1.	The entitlements assigned to an identity which are misused or hijacked

2.	The inappropriate assignment of entitlements and their potential abuse
 
3.	Any access and entitlement change made outside of established Identity Governance controls and oversight.
 
4.	Misuse of the Identity Governance system itself to compromise the environment

IoC Analysis falls into two types:
a. Reconciliation of their access to the entitlements they are authorised to
b. Was the user behaviour  and their interaction with resources appropiate (risky behaviour of a compromised account) - this is more difficult

To help with this:
1. Maintain a full map of accounts back to users using an Identity Governance solution
2. Minimize the number of service accounts associated with an identity
3. Use a directory bridge to authenticate with one centralized authoritative source, like AD
4. Avoid sharing credentials (especially administrator or root) with multiple identities


## Identity Attack Vectors

### Methods

**Electronic**

1. Vulnerabilities and Exploits – Software flaws that can lead to exploitation and ownership of an account
2. Misconfigurations – Poor configuration hygiene that can allow an attacker to hijack or create accounts
3. Privileged Attacks – Credential and password attacks based on poor account hygiene that give a threat actor unintentional access
4. Social Engineering – Broad electronic misuse to target a person to obtain sensitive information

**Physical**

1. Imposter – A physical representation of another person for the sake of inappropriate access
2. Documentation – False physical paperwork designed to invoke a state of compromise and mislead the target to provide information or access
3. Audible – Verbal command or responsive social engineering typically done over the phone or via an always-listening microphone to capture sensitive information or grant unintended privileges
4. Biometric  – The theft and malicious implementation of biometric data to gain access or compromise additional datasets

### Tactics
Tactics for identity theft can be performed by
* The art of hacking one person at a time by any means available to the threat actor including targeted attacks with detailed information about the user
* Bulk premeditated attacks using techniques like credential stuffing or brute force attacks to compromise vulnerable accounts
* Targeting vendors and the supply chain or contractors and seasonal workers or simply “fuzzing” the externally available APIs – basically attacking anything that is available and accessible outside of the organization and vulnerable to an attack due to insecure credential practices and dormant accounts.

* Interception – Passwords are captured as they are transmitted electronically through email, the network, and even SMS texts. This includes SMS cloning, SIM-jacking or other forms of hijacking and man-in-the-middle attacks.
* Brute Force – Automated guessing of passwords using dictionaries or other related password libraries (often called Rainbow Tables) that target password reuse.
Searching – The manual or electronic searching of passwords stored in insecure files, scripts, or other inappropriate electronic medium. This also falls under the category of sensitive, unstructured data abuses.
* Manual Guessing – Based on social engineering and knowledge of the identity, a threat actor will try to manually guess the password for an account.
* Social Engineering – Threat actors use human trust and social interaction to trick an identity into revealing credentials or other sensitive information.
* Stealing Passwords  – The theft of passwords that are insecurely stored on paper or other non-electronic media. This could be as simple as posting a secure Wi-Fi password on the whiteboard of a conference room or the now mythical post-it note under the keyboard.
* Shoulder Surfing – Physically observing someone typing in their password by looking over their shoulder. This could also be done electronically when a camera either in the user’s device or close to a desk has been compromised.
* Key Logging – Malware used to capture sensitive keystrokes, including passwords, as they are being entered and then transmitted to or retrieved by the threat actor for later reuse.


### Implications

### Privileges

Privlidge accounts can be used in attack chains

![Privilidge Attach Chain](https://i.imgur.com/oTp69vc.jpg)

With this in mind, here are the definitions for each user account type that can be under IAM management:
1. Privileged User – A privileged user is typically the administrator or root for a resource.
2. Super User – A super user (or superuser) has elevated privileges in various graduations above a standard user, but does not have full administrative capabilities.
3. Standard User – A standard user is void of all elevated privileges except for normal runtime of a resource.
4. Guest – A guest is the lowest form of access and is typically below a standard user. Interaction with a guest account only provides basic services.
5. Anonymous – Control access to specific resources only using an account with a null password or keys not exposed to the end user.
6. Disabled – A disabled account may have any level of privileges, but is explicitly denied access and interaction with assigned resources.
7. None – No privileges at all and may not even be defined as an identity or account.

## Identity Management Controls in the Cyber Kill Chain
