# Enterprise Identity Lifecycle Management on Okta

### Building the Foundation of Enterprise Identity

---

## Overview

This project demonstrates an enterprise Identity Access Management (IAM) implementation utilizing Active Directory, Okta Universal Directory, Identity Engine, SCIM provisioning, and automated lifecycle management. The objective is to establish a centralized identity platform capable of synchronizing users from a directory source, managing identity attributes, automating access decisions, and provisioning downstream application accounts throughout the identity lifecycle.

The implementation focuses on identity synchronization, profile mastering, attribute governance, automated group membership, and account provisioning to simulate how enterprise organizations manage user identities at scale.

---

## Architecture

The environment consists of the following components:

1. Windows Server with Active Directory
2. Okta Active Directory Agent
3. Okta Universal Directory
4. Enterprise Groups
5. Identity Engine Group Rules
6. Attribute Mapping & Profile Mastering
7. SCIM Provisioning

### Identity Flow

```text
Active Directory
       │
       ▼
Okta AD Agent
       │
       ▼
Okta Universal Directory
       │
       ▼
Attribute Mapping & Profile Mastering
       │
       ▼
Identity Engine Evaluation
       │
       ▼
Group Membership Assignment
       │
       ▼
SCIM Provisioning
       │
       ▼
Downstream Applications
```

---

## Components

### Active Directory

Active Directory serves as the authoritative directory source containing enterprise users and groups. User identities originate within the directory and are synchronized to Okta through the Okta Active Directory Agent.

Key responsibilities:

* User management
* Group management
* Identity source
* Enterprise directory services

---

### Okta Active Directory Agent

The Okta AD Agent establishes connectivity between Active Directory and Okta.

The agent makes outbound connections to Okta and imports:

* Users
* Groups
* Attribute changes
* Lifecycle events

This eliminates the need for inbound firewall rules while maintaining continuous synchronization between the directory and the IAM platform.

---

### Universal Directory

Universal Directory serves as the centralized identity repository within Okta.

Once synchronized, Active Directory users become Okta users and are managed through a unified identity profile.

Universal Directory enables:

* Identity aggregation
* Profile management
* Attribute storage
* Identity governance
* Lifecycle management

---

### Attribute Mapping & Profile Mastering

A user is a collection of attributes.

Attributes from Active Directory are mapped into Okta profiles and become available for authentication, authorization, provisioning, and downstream application integrations.

Examples include:

* First Name
* Last Name
* Email
* Department
* Manager
* Employee Type
* Custom Attributes

Profile mastering determines which system owns a user's identity data.

Attribute Level Mastering (ALM) extends this concept by allowing ownership to be defined at the individual attribute level.

This ensures:

* Accurate identity data
* Consistent synchronization
* Controlled attribute ownership
* Reliable downstream provisioning

---

### Groups

Groups represent collections of users with shared responsibilities or access requirements.

Example groups:

* IAM Engineering
* IT Help Desk
* Human Resources

Groups simplify access management by allowing permissions and applications to be assigned collectively rather than individually.

---

### Identity Engine Group Rules

Group Rules automate identity provisioning by dynamically assigning users to groups based on their attributes.

The Identity Engine continuously evaluates user profiles and determines whether a user satisfies defined business conditions.

Example conditions:

* Department equals Human Resources
* Manager equals Monica
* Employee Type equals Intern
* Certification requirements met

Benefits include:

* Automated access assignment
* Reduced administrative overhead
* Consistent role management
* Dynamic access updates

---

### Identity Provisioning

Identity provisioning focuses on identity changes occurring within the IAM platform.

Examples include:

* New employee onboarding
* Department transfers
* Manager changes
* Role changes
* Employee termination

As identity attributes change, the Identity Engine reevaluates the user and updates access accordingly.

---

### SCIM Account Provisioning

System for Cross-domain Identity Management (SCIM) automates account lifecycle management within downstream applications.

Once a user receives access through group membership and application assignments, SCIM performs account-level actions automatically.

Supported lifecycle events include:

* Account creation
* Profile updates
* Account suspension
* Account reactivation
* Account deprovisioning

SCIM eliminates manual account administration and ensures application accounts remain aligned with identity changes.

---

## Key Concepts Demonstrated

* Active Directory Integration
* Identity Synchronization
* Universal Directory
* Profile Mastering
* Attribute Level Mastering
* Attribute Mapping
* Identity Engine
* Dynamic Group Rules
* Identity Provisioning
* Account Provisioning
* SCIM
* Lifecycle Management
* Joiner-Mover-Leaver (JML)
* Role-Based Access Control (RBAC)

---

## Technologies Used

| Technology               | Purpose                          |
| ------------------------ | -------------------------------- |
| Active Directory         | Enterprise Directory Services    |
| Windows Server           | Directory Infrastructure         |
| Okta AD Agent            | Directory Synchronization        |
| Okta Universal Directory | Centralized Identity Repository  |
| Okta Identity Engine     | Identity Evaluation & Automation |
| Groups                   | Access Management                |
| Group Rules              | Automated Provisioning           |
| Profile Editor           | Attribute Management             |
| SCIM                     | Account Provisioning             |
| RBAC                     | Access Control                   |

---

## Project Outcomes

* Integrated Active Directory with Okta
* Established Active Directory as a profile source
* Implemented profile and lifecycle sourcing
* Configured attribute mappings and schema management
* Implemented attribute-level mastering
* Created enterprise groups and access structures
* Automated group membership using Identity Engine rules
* Enabled identity provisioning workflows
* Configured SCIM-based account provisioning
* Demonstrated end-to-end identity lifecycle management

---

## Skills Demonstrated

* Identity & Access Management (IAM)
* Identity Lifecycle Management
* Active Directory Administration
* Okta Administration
* Universal Directory
* Identity Governance
* Identity Provisioning
* Account Provisioning
* SCIM
* RBAC
* Attribute Management
* Enterprise Identity Architecture
* Access Automation
* Identity Operations

