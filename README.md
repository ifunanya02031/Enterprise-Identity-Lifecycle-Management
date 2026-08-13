# Enterprise Identity Lifecycle Management with Okta

## Overview

This project demonstrates an end-to-end Enterprise Identity Lifecycle Management solution using Okta as the central Identity Provider (IdP). The lab simulates a real-world identity architecture where user identities originate in Active Directory, are synchronized to Okta, enriched through identity governance and attribute management processes, and automatically provisioned to downstream applications through SCIM.

The objective of this project is to showcase core Identity and Access Management (IAM) concepts including identity synchronization, group-based access control, automated provisioning, profile mastering, attribute mapping, and lifecycle automation.

---

## Architecture

The identity lifecycle follows the workflow below:

1. User accounts and groups are created and managed in Active Directory.
2. The Okta Active Directory Agent synchronizes identities from Active Directory into Okta.
3. Okta Universal Directory serves as the centralized identity store.
4. Groups are used to organize users and drive access decisions.
5. Group Rules automatically assign users to groups based on profile attributes.
6. Profile Schema, Attribute Mapping, and Attribute-Level Mastering ensure identity data is standardized and governed.
7. SCIM provisioning automates account creation, updates, and deprovisioning in downstream applications.

---

## Technologies Used

| Technology               | Purpose                                           |
| ------------------------ | ------------------------------------------------- |
| Windows Server           | Hosts Active Directory                            |
| Active Directory         | Authoritative source for users and groups         |
| Okta AD Agent            | Synchronizes AD identities into Okta              |
| Okta Universal Directory | Centralized cloud identity repository             |
| Okta Identity Engine     | Policy and lifecycle automation                   |
| Okta Groups              | Access management and authorization               |
| Group Rules              | Automated group membership assignment             |
| Profile Editor           | Identity schema and attribute management          |
| SCIM                     | Automated account provisioning and deprovisioning |

---

## Key IAM Concepts Demonstrated

### Active Directory Integration

A Windows Server was configured with Active Directory containing users and security groups. Active Directory serves as the authoritative identity source for workforce identities.

### Identity Synchronization

The Okta Active Directory Agent was deployed to establish a secure connection between Active Directory and Okta. User and group objects are synchronized into Okta Universal Directory without exposing domain controllers directly to the internet.

### Universal Directory

Okta Universal Directory acts as the centralized identity repository where user profiles are consolidated, normalized, and managed throughout the identity lifecycle.

### Group-Based Access Control

Groups are leveraged to simplify authorization and access management. Access decisions can be made based on group membership rather than assigning permissions directly to individual users.

### Automated Group Membership

Okta Identity Engine Group Rules automate user placement into groups based on profile attributes. This reduces manual administration and ensures consistent access assignment.

Examples include:

* Department-based group assignments
* Job title-based access
* Location-specific access controls
* Role-based access provisioning

### Profile Schema Management

Custom attributes were created and managed within the Okta Profile Schema to support downstream application requirements and identity governance processes.

Examples include:

* Department
* Employee Type
* Job Title
* Cost Center
* Location

### Attribute Mapping

Attribute mappings were configured between Active Directory and Okta to ensure identity information remains consistent across systems.

This process demonstrates how identity data is transformed, normalized, and propagated throughout the environment.

### Attribute-Level Mastering

Attribute-Level Mastering was implemented to define the authoritative source for specific user attributes.

Examples:

| Attribute                      | Master Source    |
| ------------------------------ | ---------------- |
| First Name                     | Active Directory |
| Last Name                      | Active Directory |
| Department                     | Active Directory |
| Application-Specific Attribute | Okta             |

This approach ensures data integrity while supporting multiple identity sources.

### SCIM Provisioning

System for Cross-domain Identity Management (SCIM) was enabled to automate the identity lifecycle within downstream applications.

Provisioning events include:

* Account Creation
* Attribute Updates
* Role Changes
* Group Membership Changes
* Account Deactivation
* Account Deprovisioning

This eliminates manual account management and helps ensure users maintain appropriate access throughout their employment lifecycle.

---

## Identity Lifecycle Flow

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
Attribute Mapping & Schema Management
       │
       ▼
Group Rules & Automated Membership
       │
       ▼
SCIM Provisioning
       │
       ▼
Downstream Applications
```

---

## Skills Demonstrated

* Identity and Access Management (IAM)
* Identity Lifecycle Management
* Okta Administration
* Active Directory Integration
* User Provisioning & Deprovisioning
* SCIM Configuration
* Universal Directory Management
* Group-Based Access Control (GBAC)
* Attribute Mapping
* Profile Schema Design
* Attribute-Level Mastering
* Identity Automation
* Access Governance Fundamentals

---

## Learning Outcomes

By completing this project, I gained hands-on experience designing and implementing an enterprise identity lifecycle workflow using Okta and Active Directory. The project demonstrates how organizations can automate identity provisioning, enforce consistent access controls, govern identity data, and streamline user onboarding and offboarding through centralized identity management.
