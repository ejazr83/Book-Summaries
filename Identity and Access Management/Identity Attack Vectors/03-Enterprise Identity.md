
## The Five A's of Enterprise IAM

  - Authentication: Enabling users to prove they are who they claim to be
  - Authorization: Ensuring that users, once authenticated, are tightly governed in what they can access and do
  - Administration: Managing the process and policies of IAM systems and ideally automating integrations with other enterprise functions
  - Analysis: DEtecting instances of improper or faulty credential usage and triggering additional controls
  - Audit: Looking back across the identity life cycle to review events and confirm that an IAM system is being used properly
 
 
## Understanding Enterprise Identity

 - Identity can be assigned to humans as well as machines
 - Individual machine accounts and credentials must never be shared although it may happen in practice. This needs to be managed
 - Threat actors usually target **Personas** or groups of people with similar roles to be effective. Eg: sales, admin staff, executives
 - Accounts and Credentials are used to electronically identify and for a logical identity of a person

### Users
**Key Point** Enterprise IAM solutions help by managing relationship between identities, accounts and privileges by modeling and managing local persona and classification of people

**Key Point** Best Practices for IAM solutions is not to have a single point of failure where threat actors can insert himself into a one-to-one relationship of a person and their associated account or logical identity
  Examples: 
    - Identity designator (identifier) should not be used for authentication or authorization
    - Identifiers are only for reference and can be alphanumeric, electronic or biometric (eg: email address, SID)
    - Storage of designators / identifers should be protected even if public information as they can be linked to PII
    - Usually implemented in enterprises as employee ID number
    
 ### Applications
 
 Most Applications don't have an identity assigned on its own. Although it will have various accounts that in turn will have owners in order to operate the application and perform actions with delegated rights or authorization models
 
 However, applications that impersonate a person (eg: chat bots or RPAs) should have an identity assigned.
 **Key Point** Such application identities should follow the following principles:
    - Application identities should be assigned when software emulates human behavior or can inter-operate with a person on its own
    - All such identities should have a human owner assigned to manage their life cycle
    - Application identities should follow the same criteria as humans / users except
        - Personas or privs should be strictly limited to just the tasks they perform
        - Application logs should be strictly monitored for any access occurring outside of designated tasks
        - Mapping of application to identity should be 1:1 to enable digital forensics if required
 
 
### Machines
Similar to applications, if machines mimic human personas (physical or electronic) it should have an identity assigned to it. Ultimately its a business decision and is risk based depending on the harm a compromise can cause.
Identities should not be assigned to machines when the risks are strictly electronic, and attack vectors are similar to any other network device.
Sometimes it can be a grey area, like many IoT devices.

### Ownership
 - Every Identity must have an owner. For Human's, they are the owner of their own identity
 - For non-humans, they should have a human owner(s) assigned
      - The owners of a machine or application identity are responsible for its runtime. Owners are not necessarily in charge of the resource’s life cycle, maintenance, and behavior. This is the same as being a parent or guardian of a potentially mischievous minor.
      - Ownership can be a one-to-many relationship and not explicitly assigned to a single person. Ownership can be assigned to teams, departments, or even other entities outside of the organization.
      - Owners have explicit control over their identities and their associated technology implementation. This includes everything from cradle-to-grave operations of the identity and its usage.
      - Owners are basically responsible. In the world of corporate responsibility and audit, being able to assign ownership and responsibility is key to defining and maintaining controls and oversight.
      
### Automation
  - Automation requires identities that can operate autonomously or under strict control including their lifecycle
  - Concept of personas should be defined and expanded to cover automation scenarios (i.e. is the "automation action" doing something on behalf od a user or on its own and requires its own identity?)
  - Roles or groupings of an entitlement package can be used to assign it automatically and reduce inconsistencies
  - Automation simplifies classification in a consistent way and enforce policies
  
### Types of Accounts

Identity --> People, Application or Machine

Common Accounts | Typical Credentials | Key Point
---|---|---
Local|Username/Password| Local accounts usually are not centrally managed and may share username and credentials <br/> Where possible, all local accounts should have unique username and credentials or at minimum the credentials <br/> This will be mgmt overhead without a PAM solution to manage local accounts, so focus on high priv / high asset local accounts
Centralised| Username/Password, SSO and MFA | Typically AD or LDAP accounts <br/> Domain admin or central high priv accounts must be protected with strong authentication <br/> This should never be shared and requires unique account for each user <br/> proper mitigation for a compromised DA account is usually building entire environment from scratch!
Functional|Username/Password, Certificates, keys| Usually used for **automated account/identity functions** <br/> Should be created with least privilege model and limited by environments, assets and activities required <br/> Typically fall outside JIT or PAM solutions as they are "always on"
Managed or proxy accounts | Username/Password or Keys|Usually used to manage functional accounts <br/> This account is managed by another account type (eg: MSA in SQL or delegated access to former employee account or contractors) 
Service|Username/Password | Can be a local or central account with some admin privilege to access resources <br/> Should not have interactive logon rights, interactive shell access and should be carefully monitored
Application to Application|Username/Password, Certificates or Keys| Not same as service accounts (provide runtime credentials required for app to execute <br/> application management accounts provide credentials to inter-operate with other applications <br/> Usually should not have an identity associated with these type of accounts <br/> But they should also have Owner and lifecycle management <br/> To manage appropriately, these accounts can be managed in an IGA / PAM solution and ensure account credentials are synced in all places when changed
Cloud|Username/Password or Keys, SSO and MFA | Many of the points above apply <br/> What cloud accounts are used to access matters, for example biometric data that can never be changed warrants high protective measures


### Entitlements

These are the technical implementation of the access controls to a resource
- Simple Entitlement: Very atomic, Eg: AD group membership, access to Network
- Complex Entitlement: Anything else, usually part of applications eg: SAP R3 role

### Roles

Is a collection of people or access defined and maintained for manageability and good governance. Enterprise Role definitions are critical management controls that need to be secured and managed appropriately.

A two tier model for Business roles and IT roles should be used to simplify role modelling. These two are then linked to form an Enterprise rol definition.

Ultimate goal is to connect IT roles to Business roles and use the business role to identity relationships to complete the linkage back to Identity.

Should have a concept of Mandatory/default and Optional linkage/ relationships between Business and IT roles
- Mandatory - if you are in this particular business role, you automatically get the entitlements assigned to this set of IT roles
- Optional - these IT roles are permitted to be associated, but not by default

**Aim is to give out less default entitlements as default
** For optional roles, pre-approval concept can be used to quickly give access to users while supporting least privilege

Business Roles: 
  - Use Identity attributes to filter into business role groupings
  - Uses organizational information
  - Should have Business owners with some meta data about who, when and why this business group exists. Can come from HR systems as well
  - This is usually hierarchical as well and should make sense to business users who directly own them and manage business role lifecycle

IT Roles:
  - Collects together a group of entitlements usually from a resource point of view.
  - Lives with the application owner and specify the specific configuration options
  - Should be able to stand alone (i.e. not linked to business role) and uses runtime identity attributes (eg: location, authentication type etc)
  - Can also use nesting and hierarchies to allow for complex configurations and encapsulate larger deployments
  - IT technical roles should also have defined owners usually someone close to the resource or configuration
  - IT roles owners are responsible for lifecycle and approving their definition and configuration changes

![Two tier Enterprise Role Model](https://i.imgur.com/8h4wrNS.png)

## Bots
  - Identity governance should be used for Bots performing critical actions
  - Requires building out an inventory and having a catalog of their presence, purpose and access requirements
  - For persistent bots treat it like an identity for other accounts, catalogue them and manage their lifecycle
