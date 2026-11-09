# Entra-ID-User-Management-Lab



## Project Overview



This repository demonstrates practical identity administration and access management workflows using Microsoft Entra ID in a cloud-only test environment.



The project focuses on common IT Support and Junior IAM responsibilities, including user lifecycle management, access provisioning, account administration, password resets, troubleshooting, and audit log verification.



All practical administrative operations were performed through the Microsoft Entra Admin Center.



## Lab Environment



- **Identity Platform:** Microsoft Entra ID

- **Environment:** Cloud-only test tenant

- **Administrative Interface:** Microsoft Entra Admin Center

- **Identity Synchronization:** Not configured

- **On-premises Active Directory Domain Services:** Not deployed

- **Management Method:** Web-based administration



For environment details and limitations, see [Lab Environment](documentation/Lab-Environment.md).



## Implemented Workflows



| Workflow | Description | Documentation |

|---|---|---|

| Joiner | New employee account creation, attribute configuration, and group assignment | [Joiner Workflow](workflows/Joiner-Workflow.md) |

| Mover | Department transfer and adjustment of group memberships | [Mover Workflow](workflows/Mover-Workflow.md) |

| Leaver | Account disablement, session revocation, and group access removal | [Leaver Workflow](workflows/Leaver-Workflow.md) |

| Password Reset | Administrative password reset and audit verification | [Password Reset Workflow](workflows/Password-Reset-Workflow.md) |

| Account Lockout Troubleshooting | Investigation of available sign-in activity and account status, with documented troubleshooting procedures | [Account Lockout Troubleshooting](workflows/Account-Lockout-Troubleshooting-Workflow.md) |

| Access Request & Approval | Request documentation, simulated approval, least-privilege review, access provisioning, and audit verification | [Access Request Record](scenarios/AR-001-Access-Request/Access-Request-Record.md) |



## Evidence and Validation



Each implemented scenario includes supporting evidence where applicable:



- Microsoft Entra ID screenshots.

- Evidence reports describing actions performed.

- Administrative audit log records.

- Validation results and documented limitations.



Evidence is organized by scenario in the [evidence](evidence/) directory.



## Key Skills Demonstrated



- Microsoft Entra ID user administration.

- Joiner, Mover, and Leaver lifecycle processes.

- Security group and membership management.

- Role-based access control concepts.

- Least-privilege access principles.

- Access request documentation and approval procedures.

- Account disablement and sign-in session revocation.

- Administrative password reset procedures.

- Sign-in and audit log investigation.

- Evidence collection and operational documentation.

- Distinguishing verified results from untested procedures and simulated activities.



## Project Structure



```text
Active-Directory-User-Management-Lab/
|
+-- documentation/
|   +-- Lab-Environment.md
|
+-- evidence/
|   +-- Account-Lockout-Troubleshooting/
|   +-- AR-001-Access-Request/
|   +-- Joiner-Onboarding/
|   +-- Leaver-Offboarding/
|   +-- Mover-Department-Transfer/
|   +-- Password-Reset/
|
+-- scenarios/
|   +-- AR-001-Access-Request/
|   +-- Mover-Department-Transfer/
|
+-- workflows/
    +-- Account-Lockout-Troubleshooting-Workflow.md
    +-- Joiner-Workflow.md
    +-- Leaver-Workflow.md
    +-- Mover-Workflow.md
    +-- Password-Reset-Workflow.md
```



## Scope and Limitations



This project uses a cloud-only Microsoft Entra ID test tenant. It does not represent a deployed on-premises Active Directory Domain Services environment or a hybrid identity infrastructure.



The following activities were not implemented or independently verified:



- On-premises AD DS administration against a live domain controller.

- Hybrid identity synchronization.

- Microsoft Graph PowerShell automation.

- Automated manager approval processing.

- Effective access to production applications or resources.

- Successful end-user authentication following the administrative password reset.

- An actual account lockout and subsequent recovery.



The Access Request approval was simulated and documented as part of the lab scenario. Group membership validation confirms directory-level assignment, not effective application access.



All practical results are documented with their corresponding evidence and limitations.



## Project Objective



The objective is to demonstrate an understanding of identity lifecycle management, access administration, basic account troubleshooting, operational controls, and auditability through practical Microsoft Entra ID exercises.



