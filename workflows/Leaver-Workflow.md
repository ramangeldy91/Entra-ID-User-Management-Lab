# Leaver Workflow - Employee Offboarding



## 1. Purpose and Scope



This document defines the Leaver workflow for managing employee offboarding and removing access to corporate resources.



The workflow ensures that:



- Employee access is revoked at the authorized termination date and time.

- User accounts are disabled to prevent further sign-in.

- Active sessions and refresh tokens are revoked.

- Security groups, application assignments, and privileged access are reviewed and removed as appropriate.

- Business data is retained or transferred according to organizational policies.

- All offboarding activities are documented and auditable.



The practical implementation in this lab uses Microsoft Entra ID cloud-only test accounts.



## 2. Roles and Responsibilities



| Role | Responsibility |

|---|---|

| HR | Provides the official termination notification and confirms the employee's termination date. |

| Manager | Confirms business requirements, data ownership, and any required handover activities. |

| IT/IAM Administrator | Reviews identity and access, disables the account, revokes sessions, and removes access. |

| Application/Resource Owner | Confirms application-specific access removal and data ownership requirements. |

| Security Team | Supports urgent or high-risk offboarding when required by organizational policy. |



**Separation of Duties:** HR confirms the employment event, authorized business representatives approve exceptions and data handovers, and IT/IAM implements the technical access changes.



## 3. Leaver Workflow



### Step 1 - HR Initiates the Offboarding Request



HR submits an official termination notification containing:



- Employee full name.

- Employee ID.

- User Principal Name (UPN) or account identifier.

- Department and job title.

- Manager.

- Employment termination date.

- Exact access termination date and time.

- Any special offboarding requirements.



The effective date and time must be clearly documented, including the applicable time zone.



**Expected result:** An authorized offboarding request is received and recorded.



### Step 2 - Review Identity and Existing Access



The IT/IAM Administrator identifies the employee's accounts using the Employee ID and verifies the account identity.



The administrator reviews:



- User accounts and associated identities.

- Security group memberships.

- Directly assigned application access.

- Administrative roles and privileged permissions.

- Active sessions and available sign-in information.

- Assigned licenses.

- Associated devices, where device management is available.

- Ownership of business resources and data.



The administrator must distinguish between group membership and actual application or resource permissions.



**Expected result:** The employee's access inventory is documented before revocation.



### Step 3 - Confirm Termination Details and Exceptions



The IT/IAM Administrator verifies the termination date and time with the authorized HR or management request.



Any request to extend access beyond the scheduled termination time must:



1. Be formally documented.

2. Have approval from the authorized business representative.

3. Include a specific business justification.

4. Identify the exact resources that must remain accessible.

5. Specify an expiration date and time.

6. Receive additional Security or resource-owner approval when required.



Temporary access exceptions must be time-bound and limited to the minimum required permissions.



An administrator must not extend access based solely on an informal or verbal request.



**Expected result:** The access termination schedule and any approved exceptions are confirmed.



### Step 4 - Disable the User Account



At the authorized access termination time, the IT/IAM Administrator disables the user's account.



In Microsoft Entra ID, this is performed by setting the account's sign-in permission to disabled.



The administrator must verify that the account is no longer permitted to sign in.



For urgent or security-sensitive terminations, account disabling must follow the organization's emergency offboarding procedure.



**Expected result:** The user account is disabled and new sign-ins are blocked.



### Step 5 - Revoke Active Sessions and Remove Access



After disabling the account, the IT/IAM Administrator revokes the user's sign-in sessions and refresh tokens.



The administrator then reviews and removes access assignments as appropriate:



- Security group memberships.

- Direct application assignments.

- Administrative roles.

- Privileged access assignments.

- Other identity-based permissions.



Access must be reviewed across the relevant systems, not only Microsoft Entra ID.



Some applications maintain their own sessions or access tokens. Application-specific session termination or credential revocation may therefore be required.



**Expected result:** The user's access assignments are removed or disabled, and session revocation is performed and documented. Relevant audit events are reviewed where available.



### Step 6 - Data Retention and Ownership Transfer



Before deleting the account, the relevant business owners determine what data must be retained or transferred.



Activities may include:



- Transferring ownership of business files.

- Preserving required email and mailbox data.

- Transferring ownership of shared resources.

- Retaining records according to organizational and legal requirements.

- Documenting the responsible person for retained data.



The IT/IAM Administrator must not independently delete business data or make retention decisions.



Account deletion must follow the approved retention and offboarding policy.



**Expected result:** Required business data is preserved and ownership responsibilities are documented.



### Step 7 - Validate Access Revocation



The IT/IAM Administrator verifies that the offboarding actions were completed successfully.



Validation includes:



- Confirming that the user account is disabled.

- Verifying that sign-in sessions were revoked.

- Checking security group memberships.

- Reviewing application assignments and privileged roles.

- Confirming that required access has been removed.

- Checking relevant audit log events.

- Recording any application-specific actions that remain outstanding.



Disabling an account and revoking refresh tokens do not guarantee immediate termination of every existing application session. Relevant application-specific controls must also be checked.



**Expected result:** Access revocation is verified and outstanding issues are documented or escalated.



### Step 8 - Documentation and Ticket Closure



The IT/IAM Administrator records the completed offboarding activities.



The evidence should include:



- Employee ID and account identifier.

- Offboarding request reference.

- Approved termination date and time.

- Account disablement result.

- Session revocation result.

- Removed groups, roles, and application assignments.

- Data retention or ownership transfer status.

- Audit log references.

- Exceptions, errors, and escalation details.



The ticket may be closed after all required access revocation activities are completed and outstanding responsibilities are assigned.



**Expected result:** The offboarding process has a complete and auditable record.



### Step 9 - Account Deletion



Account deletion is a separate lifecycle action and must not be confused with immediate access revocation.



The account may be deleted only when:



- The applicable retention period has expired.

- Required data has been preserved or transferred.

- Relevant business and compliance requirements have been satisfied.

- Deletion has been authorized according to organizational policy.



In Microsoft Entra ID, deleted user accounts normally enter a recoverable soft-delete state before permanent deletion.



The exact deletion schedule must follow the applicable organizational policy and platform requirements.



**Expected result:** The account is deleted only after the required retention and authorization checks.



## 4. Exception Handling



| Scenario | Required Action |

|---|---|

| Missing termination information | Pause scheduled offboarding and request clarification from HR. |

| Employee identity cannot be verified | Do not modify the account until identity is confirmed. |

| Termination time changes | Obtain documented confirmation and update the offboarding schedule. |

| Temporary access extension requested | Require documented authorization, limited scope, and an expiration time. |

| Account disablement fails | Escalate immediately and investigate the provisioning error. |

| Session revocation fails | Document the failure, retry as appropriate, and investigate application-specific controls. |

| Employee remains in security groups | Review and remove unauthorized or unnecessary memberships. |

| Application access remains active | Contact the application owner and complete application-specific revocation. |

| Data ownership is unclear | Escalate to the manager or data owner before deletion. |

| Retention requirements are unresolved | Do not permanently delete the account or associated data. |



All exceptions must be documented and tracked until resolved.



## 5. Security and Access Control Requirements



The following principles apply throughout the Leaver workflow:



- **Timely Access Revocation:** Access must be removed at the authorized termination time.

- **Least Privilege:** Retained access must be limited to explicitly approved business requirements.

- **Separation of Duties:** HR and management approve business decisions; IT/IAM performs technical actions.

- **Session Revocation:** Existing sessions and refresh tokens must be addressed separately from account disabling.

- **Data Protection:** Business data must be retained or transferred according to policy.

- **Auditability:** Administrative actions must be traceable and documented.

- **Controlled Deletion:** Permanent account deletion must follow retention and authorization requirements.



## 6. Validation and Evidence



The practical implementation of this workflow will be tested using a dedicated cloud-only Microsoft Entra ID test account.



The lab validation will cover:



- Identification of the test account.

- Review of security group memberships.

- Disabling the user account.

- Revoking sign-in sessions.

- Removing assigned security group memberships.

- Verifying the resulting account and access state.

- Reviewing relevant Microsoft Entra audit log events.



Evidence will be maintained in:



`evidence/Leaver-Offboarding/`



The evidence will include screenshots, an Evidence Report, and the results of the practical validation.



## 7. Environment Limitations



This lab uses Microsoft Entra ID cloud-only test accounts.



The following enterprise activities are documented but are not implemented through a real corporate HR or IT service management platform:



- HR termination request submission.

- Actual HR or manager approval.

- Automated termination workflows.

- Integration with an HR information system.

- Application-specific session termination.

- Enterprise device management and remote device actions.

- Corporate mailbox and business data retention.

- Permanent deletion under a real organizational retention policy.



The lab demonstrates identity account disablement, session revocation, group membership changes, and verification where supported by the available environment.



Security group membership removal does not independently prove that all application or resource access has been revoked.



No real employee information is used.



## 8. Conclusion



The Leaver workflow establishes a controlled and auditable process for employee offboarding.



By verifying the employee identity, reviewing existing access, disabling the account, revoking sessions, removing unnecessary permissions, and preserving required business data, the process reduces the risk of unauthorized access after employment termination.



Separating immediate access revocation from account deletion ensures that security requirements and data retention obligations are handled independently.



The workflow supports secure identity lifecycle management and effective access governance.


