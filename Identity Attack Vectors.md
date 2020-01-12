# Identity Attack Vectors - 2019 - O-reilly

### By Morey Haber and Darren Rolls

## Three Pillars of CyberSecurity
  1. Identity
    - Human or Machine
    - Trusted or Untrusted
    - Business or Tech role
    - Entitlement reporting
    - Inception or revocation
    
  2. Privilege
    - Admin vs Root vs Standard user
    - Least privilidge
    - Priv id mgmt
    - Session mgmt
    - Directory bridging with shared or local accounts
    - Reporting and Analytics
    
  3. Asset
    - Vulnerability Management
    - Patch Management
    - Configuration Management
    - Regulatory Compliance
    - Threat and Risk reporting
    


## Lateral Movement

Lateral movement is the ultimate aim for threat actors to find data of value or compromise additional assets and resources.

**Resource lateral movement techniques**

Resources | Privileged Attack Vector | Asset Attack Vector
---|---|---
Operating system | Credential, certifcates, or hash-based attacks | Vulnerabilities, exploits, and misconfigurations
Applications | Credential, certifcates, or application-to-application attacks | Vulnerabilities, exploits, misconfigurations, insecure architectures, and end of life
Containers | Credential, certifcates, or insecure connectivity (lack of zero trust) | Vulnerabilities, exploits, misconfigurations, insecure architectures, and agile DevOps
Virtual machines | Credential or hash- or hypervisor-based credential attacks | Vulnerabilities, exploits, misconfigurations, insecure architectures and agile DevOps, and CPU- and memory-based vulnerabilities
Accounts | Credential theft or abuse or identity theft | Credential theft, abuse, memory-scraping, and insecure credential storage 
Identities | Credential reuse, credential theft | Inappropriate account linkage

Lateral movement attacks occur due to two vectors:
1. Privilidged attacks: Password guessing , brute force, pass the hash etc
2. Asset Attacks: missing vulnerbaility, patch and config management ( Basic cyber hygiene )

*Key Point*: For Asset attacks concepts like Zero-trust or JIT and PAM will not work. Need basic cyber hygiene practices in place for asset protection

For Privilidged attack vector: concepts of Zero-trust and JIT will help in mitgation
 - *Zero trust* is a security model based on the principle of maintaining strict access controls and not trusting anyone, anywhere, at any time, even those already inside the network perimeter, by default.
 - *Just-in-time privileged access* is a strategy that aligns real-time requests for usage of privileged accounts directly with entitlements, workflow, and appropriate access policies.
 

## The Five A's of Enterprise IAM

  - Authentication: Enabling users to prove they are who they claim to be
  - Authorization: Ensuring that users, once authenticated, are tightly governed in what they can access and do
  - Administration: Manaigng the process and policies of IAM systems and ideally automating integrations with other enterprise functions
  - Analysis: DEtecting instances of improper or faulty credential usage and triggering additional controls
  - Audit: Looking back across the identity lifecycle to review events and confirm that an IAM system is being used properly
 
 
## Understanding Enterprise Identity

 - Identity can be assigned to humans as well as machines
 - Individual machine accounts and credentials must never be shared although it may happen in practice. This needs to be managed
 - Threat actors usually target **Personas** or groups of people with similar roles to be effective. Eg: sales, admin staff, executives
 - Accounts and Credentials are used to electronically identify and for a logical identity of a person

### Users
**Key Point** Enterprise IAM solutions help by managing relationship between identities, accounts and privilidges by modeling and manging local persona and classification of people

**Key Point** Best Practices for IAM solutions is not to have a single point of failure where threat acto can inser himself into a one-to-one relationship of a person and their associated account or logical identity
  Examples: 
    - Identity designator (identifier) should not be used for authentication or authorization
    - Identifiers are only for reference and can be alphanumeric, electronic or biometric (eg: email address, SID)
    - Storage of designators / identifers should be protected even if public information as they can be linked to PII
    - Usually implemented in enteprises as employee ID number
    
 ### Applications
 
 Most Applications dont have an identity assigned on its own. Although it will have various accounts that in turn will have owners in order to operate the application and perform actions with delegated rights or authorisation models
 
 However, applications that impersoante a person (eg: chat bots or RPAs) should have an identity assigned.
 **Key Point** Such applicaiton identities should follow the following principles:
    - Application identities should be assigned when software emulates human behaviour or can interoperate with a person on its own
    - All such identities should have a human owner assigned to manage their lifecycle
    - Application identities should follow the same criteria as humans / users except
        - Personas or privs should be strictly limited to just the tasks they perform
        - Application logs should be strictly monitored for any access occuring outside of designated tasks
        - Mapping of application to identity should be 1:1 to enable digital forensics if required
 
 
### Machines
Similar to applications, if machines mimic human personas (physical or electronic) it should have an identity assigned to it. Ultimately its a business decision and is risk based depneding on the harm a compromise can cause.
Identities should not be assigned to machines when the risks are strictly electronic, and attack vectors are similar to any other network device.
Sometimes it can be a grey area, like many IoT devices

### Ownership
 - Every Identity must have an owner. For Human's, they are the owner of their own identity
 - For non-humans, they should have a human owner(s) assigned
      - The owners of a machine or application identity are responsible for its runtime. Owners are not necessarily in charge of the resource’s lifecycle, maintenance, and behavior. This is the same as being a parent or guardian of a potentially mischievous minor.
      - Ownership can be a one-to-many relationship and not explicitly assigned to a single person. Ownership can be assigned to teams, departments, or even other entities outside of the organization.
      - Owners have explicit control over their identities and their associated technology implementation. This includes everything from cradle-to-grave operations of the identity and its usage.
      - Owners are basically responsible. In the world of corporate responsibility and audit, being able to assign ownership and responsibility is key to defining and maintaining controls and oversight.
      
### Automation






