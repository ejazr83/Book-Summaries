
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
2) Establish major processes such as basic controls, enterprise role management and policy evaluations
3) Advanced "predictive" governance using AI


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

![Identity Warehouse](https://i.imgur.com/6n4WLGl.png)

**Entitlement Catalog** IS the central artifact at the Identity Governance process
* Is the genric name for the technical access control facility that we care to catalog and manage
* Is simply a registry of these capabilities found across all systems
* Managing and maintaining the catalog across IG solution is of critical importance
* Meta data and attributes are key and must be protected like crown jewels 

### Full Lifecycle Management

![Overall view of LifeCycle Management processes](https://i.imgur.com/jmNg1WT.png)

Goal of LCM is to provide automation and controls for lifecycle of system and application access. LCM state model describes how the LCM process is best driven by known states and transitions between states called events. LCM **states** eg: Prehire, Hired, Terminated or JML (Joiner, Mover, Leaver) **events**

When a trigger event happens, a defined is supposed to be executed such as standard governance actions like access reviews, reapprovals, policy evaluations and standardized workflows. These workflows showed be owned by a business user. This stadnardisation allows for delegation to self-service for business users. This includes things like access requests, password resets and ability to participate in ongoing certification and verification of access.

Model Based approach to IGA: 

IGA policy models are used to capture the desired state, known best practice configuration, and an inventory of controls and governance actions. 
These models are abstract representations of how accounts and privileges should be set, approved, audited, and used to some known state. 
Examples of IGA policy models include the entitlement catalog, provisioning schemas, approval and ownership records, audit requirements, role models, lifecycle triggers, and Separation of Duty rules.

Enterprise Roles are a critical model in IGA.

A good role model will provide a place to define, verify, and reconcile access, a place to define the correct configuration or entitlement, a place to establish assignment approvals, and a place to track the ongoing state of access across potentially thousands of target applications, hundreds of thousands of users, and millions of entitlements.



### Provisioning and Fulfillment
Provisioning and fulfillment in a governance-based approach represents how the system assures completion of an action, regardless of how it gets delivered across the “last mile.”

![Provisioning Broker](https://i.imgur.com/ZEQePmT.png)

A provisioning engine has to be sophisticated and needs to have retry, rollback and ongoing assignment and de-assignment options. Behaviour under failure scenarios is key. Particulalry around entitlement package rollbacks if one of the provisioning actions fails. And how many times a retry attempt must be made.

**Key Point** If the provisioning system only creats accounts and does not undertand account attributes and roles then its an "account only" provisioning. This should be avoided where possible for a full enterprise provisioning option which can assign roles as well.

### Governance Policy Enforcement
Three common / main types of policies that drive access compliance. These should be owned by the business and should also include remediation advice for violations

1. Seperation of Duty (SoD) policies: Defining roles that cant be owned by the same person. Eg: Invoice creation and payment or dev, testing and operations.

2. Account policies: Basic policies on dormant accounts, provisioning pre-reqs. This could also include tracking multiple accounts and account creep

3. Entitlement policies: Defines a specific set of applications that someone should have access to eg: manager and non-manager applications. Or entitlement package for department A vs department B. Allows for embedding checks and balances and making sure access restrictions are enforced.

**Preventative vs Detective Policies:** You can use SoD rules for preventative policy controls so that bad access provisioning does not happen in the first place. Detective rules are passive and usually run in batches (end of month or end of quarter) Less intrusive as well as it doesnt break the provisoning process. You will need both


### Certification and Access Reviews
This is an important part of the Identity Governance process. It enables managers or delegates to review and verify access required in a consistent and highly auditable way

Avoid **pitfall** of ruber stamp approvals. This can be done by designing campaigns which are business frinedly and moving towards an access review "by exception" policy or aggregating entitliements into a role.

![Evolution of Access Certifications](https://i.imgur.com/uOz6vod.png)

A general move towards preditive role based access, where even the "role engineering" process is using Machine learning and AI to come up with entitlement packages speeding up the traditionally tedious process of "role discovery and engineering"

### Governing unstructured Data
Managing access to files is usually considered unstructured data

Requires combination of data discovery and classification as well as permission management capabilities

### Self Service and Delegation
Four items to address
* Define requestable units that users can self-service request and get automatic access
* Delegate to authorised indviduals (eg: Managers, HR etc) who can request and get access on behalf of the user rather than coming to IT. These are usually those who would approve access requests and verify access certifications as well
* Overlay of Data driven controls and governance so that seperation of duties and other preentative access controls are maintained
* Request tracking and reporting for all such requests

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
