# Lab Environment



## 1. Overview



This project was performed in a cloud-only Microsoft Entra ID test tenant.



All practical identity administration activities were carried out through the Microsoft Entra Admin Center web interface.



**Environment Details:**



| Component | Description |

|---|---|

| Identity Platform | Microsoft Entra ID |

| Environment Type | Cloud-only test tenant |

| Administrative Interface | Microsoft Entra Admin Center |

| Access URL | https://entra.microsoft.com/ |

| Management Method | Web-based administration |

| Licensing | Free Entra ID capabilities; no paid Entra ID licenses were available for the lab activities |

| Identity Synchronization | Not configured |

| On-premises Infrastructure | Not available |



## 2. Administrative Tools



The following interface and capabilities were used during the practical exercises:



- Microsoft Entra Admin Center

- User account management

- Security group management

- Group membership administration

- Account enablement and disablement

- Password reset operations

- Sign-in log inspection

- Audit log investigation



All administrative changes were performed through the Entra Admin Center.



## 3. Test Identities and Groups



The lab used dedicated test identities and security groups to demonstrate identity lifecycle and access management processes.



**Test identities:**



| Test Identity | Employee ID | Purpose |

|---|---|---|

| IAM Lab User 01 | LAB-USER-001 | Mover workflow |

| Emily Carter | LAB-USER-002 | Joiner workflow |

| Leaver Test User 01 | LAB-USER-003 | Leaver workflow |

| Password Reset Test User 01 | LAB-USER-004 | Password reset and access request scenarios |



**Security groups:**



- `GRP-IT-Support-Basic`

- `GRP-Finance-Basic`



These identities and groups were created exclusively for laboratory exercises.



## 4. Practical Environment Scope



The following operations were performed and verified in Microsoft Entra ID:



- User creation and attribute configuration.

- Security group membership assignment.

- Department transfer through group membership changes.

- Account disablement and group access removal.

- Sign-in session revocation.

- Administrative password reset.

- Access request provisioning.

- Review of relevant audit log events for administrative changes.

- Inspection of available sign-in activity and account status.



Evidence screenshots and individual reports are maintained in the `evidence/` directory.



## 5. Environment Limitations



The laboratory does not include:



- An on-premises Active Directory Domain Services environment.

- A Windows Server Domain Controller.

- Hybrid identity synchronization through Microsoft Entra Connect.

- Microsoft Graph PowerShell automation.

- Azure resource administration through Azure Portal.

- A production HR information system or automated approval platform.

- Production application integrations for effective access testing.



Some operational procedures, including on-premises AD DS account lockout investigation, are documented for technical reference but were not executed against live infrastructure.



Manager approval in the Access Request scenario was documented as a lab simulation rather than a real approval process.



Group membership verification confirms directory-level assignment only. It does not independently establish access to a specific application or resource.



## 6. Security and Testing Principles



The lab follows these principles:



- Use dedicated test identities instead of personal or production accounts.

- Apply least-privilege access principles.

- Verify administrative changes through available audit records.

- Preserve evidence of relevant operations.

- Avoid storing passwords or authentication secrets in project documentation.

- Clearly distinguish executed tests from documented procedures and simulated scenarios.



## 7. Project Scope Statement



This project demonstrates practical identity administration and access management workflows using Microsoft Entra ID in a cloud-only test environment.



It is not presented as a production Active Directory infrastructure, a hybrid identity deployment, or a complete enterprise IAM implementation.

