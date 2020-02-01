
## Identity Governance Defined

The three question triangle of Identity Governance

1. Who currently has access? - should be the starting, usually the easiest
2. Who should have access? - the next thing and next difficult question to answer
3. How is access being used? - critical input for overall governance loop nut requires first two steps to be begin answering this

At a basic level the Identity governance is managing access for people to the right data
People <---- Access ----> Data

However, this relationship spans multiple enterprise systems, are sometimes embedded in applications and may often have externalised methods of control for SSO and ABAC services.

Identity Governance and Administration solutions help in managing this complexity including JML (Joiner, Mover, Leaver) lifecyle

## Identity Governance Process
1) Establish visibility and Context over Current State
2) 


### Visibility, Connectivity, and Context
**Visibility** provides information on who as access at any given point in time. A critical first step
**Context** provides the meaning of access in a business point of view. The technology access control model must be linked to business meaning
**Connectivity** is ultimate required to all source sof identity to gain **visibility** and establish **context**

Approach to connectivity to multiple HR systems, Contractor systems, partner systems etc is required
1) Direct API - using a standard interface from directory source
2) Shared repo - A purpose built data repo for sharing identity and account information
3) Standards based - Using industry standards for protocols, data sources can exchange identity information (eg: SCIM)
4) Custom application - Using custom code to create connectors or share information (eg: CSV manual feed)

**Key Point** For an Identity Governance system to make any form of connection to an external application or system, it requires its own authorization. Use of shared repos to perform access control decisions (eg: AD groups for access control). This can become a challenge to manage in the long term because group membership is disconnected from the application. An IGA solution should instead help in this.

**Key Point** Governance service manages the end-user credentials for connectors often requires highly privileged API tokens and application accounts. These accounts and credentials must themselves be stored, managed, and audited. As a best practice, these credentials should be in a PAM vault external to the Identity Governance engine

**Key Point** An Account correlation process is necessary to ensure every account is linked back to a human
Accounts that cant be linked back are orphan accounts which are significant security weakness. A common finding in most breach forensics is use or creation of orphan accounts through the cyber kill chain.
An identity warehouse must ensure ongoing governance and security to instrument and automate detection and rapid resolution of orphan accounts

 Summary of the overall account and privilege correlation. Identities, accounts, and privileges continually flow into the system, and items that don’t connect back to a human are flagged for the attention of application and system administrators
<Diagram>

### Full Lifecycle Management


### Provisioning and Fulfillment


### Governance Policy Enforcement


### Certification and Access Reviews


### Governing unstructured Data


### Self Service and Delegation


## Meeting Regulatory Compliance

 - Identity Governance provides control plane that answers the question “who has access to what.” 
 - This control plane provides the process and tracking transparency needed to reduce potential security and compliance exposure
 - Replaced paper based and manual methods with something more automated that can also help reduce the cost of compliance over time

Bests Practice towards sustainable compliance for Identity Governance

1|2|3|4|5
---|---|---|---|---
**Assess your current state**|**Build Governance Model**|**Automate Detective Controls**|**Automate Preventative Controls**|**Perform closed-loop audit on all changes**
Aggregate and correlate identity data|define policy model|access certifications|access request mgmt|aggregate data
Conduct baseline access certification|define role model|policy detection and remediation|password mgmt|Identity exceptions
 |Define risk model| |automated provisioning|provide proof of compliance