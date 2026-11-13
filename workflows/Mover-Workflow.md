# Mover Workflow - Department Transfer



## 1. Purpose



This workflow defines the process for managing employee access when an employee changes department, job role, or responsibilities.



The objective is to ensure that access rights remain aligned with the employee's current responsibilities and follow the principles of Least Privilege and Role-Based Access Control (RBAC).



## 2. Scope



This workflow covers:



- Department and role change initiation

- Access requirements review

- Manager approval

- Access provisioning

- Removal of outdated access

- Access validation

- Documentation and closure



## 3. Roles and Responsibilities



| Role | Responsibility |

|---|---|

| HR | Records the employee's department or role change and initiates the request |

| New Manager | Defines and approves access required for the new role |

| Resource Owner | Approves access to resources under their responsibility, where required |

| IAM / IT Administrator | Implements approved access changes and validates the result |

| Employee | Confirms that required business access is available |



The IAM / IT Administrator must not independently decide which business permissions an employee requires.



## 4. Workflow Procedure



### Step 1 - Initiate the Change



HR records the employee's department or role change and submits a documented access-change request.



The request should include:



- Employee name and unique identifier

- Current department and job role

- New department and job role

- Effective date of the change

- New manager

- Required access review



### Step 2 - Review Access Requirements



The new manager identifies the access required for the employee's new responsibilities.



Existing access must be reviewed individually and classified as:



- Retain - access remains necessary for the new role

- Modify - access must be changed

- Revoke - access is no longer required



Access should not be retained automatically simply because the employee previously had it.



### Step 3 - Obtain Approval



The new manager approves the required access.



Resource owners provide additional approval when required by organizational policy.



The approval must be documented before access is provisioned.



### Step 4 - Provision New Access



The IAM / IT Administrator:



1. Reviews the approved access request.

2. Identifies the appropriate security groups.

3. Adds the employee to the required groups.

4. Verifies the updated group membership.



New access should be provisioned and verified before removing existing access when the approved transition plan requires continuity.



### Step 5 - Revoke Outdated Access



The IAM / IT Administrator:



1. Identifies groups and permissions no longer required.

2. Removes the employee from outdated security groups.

3. Verifies that obsolete memberships have been removed.



Shared access required by the employee's new role should be retained when justified and approved.



### Step 6 - Validate Access



The administrator verifies:



- Required new group memberships are present.

- Outdated group memberships have been removed.

- No unnecessary access remains.

- Actual access is consistent with the approved request.



Group membership alone does not prove that access to an application or resource is functioning. Resource-level permissions must be checked separately when applicable.



### Step 7 - Document and Close the Request



The administrator records:



- Request or ticket reference

- Employee identifier

- Approved access changes

- Groups added and removed

- Administrator who performed the changes

- Execution date and time

- Validation results

- Evidence references



The request can be closed after successful validation and documentation.



## 5. Practical Lab Execution - Microsoft Entra ID



### Test Scenario



An employee transfers from IT Support to Finance.



**Test identity:** IAM Lab User 01

**User identifier:** LAB-USER-001



**Initial group membership:**



- GRP-IT-Support-Basic



**Target group membership:**



- GRP-Finance-Basic



### Actions Performed



1. Created the `GRP-Finance-Basic` security group.

2. Added `IAM Lab User 01` to `GRP-Finance-Basic`.

3. Verified that the user temporarily belonged to both IT Support and Finance groups.

4. Removed the user from `GRP-IT-Support-Basic`.

5. Verified the final group membership.



### Actual Lab Result



| Check | Expected Result | Actual Result |

|---|---|---|

| Finance group membership | Present | Verified |

| IT Support group membership | Absent | Verified |

| Final group membership | Finance group only | Verified |



**Result: PASS**



The user was successfully transferred from the IT Support security group to the Finance security group.



### Lab Limitations



This exercise demonstrates Microsoft Entra ID security group membership management.



The following activities were not performed as part of this test:



- Actual HR request submission

- Real manager approval

- Resource-owner approval

- Assignment of application or resource permissions

- Verification of access to actual Finance applications



These activities are included in the designed workflow but are not claimed as completed lab operations.



## 6. Security and Access Control Principles



- Least Privilege

- Role-Based Access Control (RBAC)

- Separation of Duties

- Approval-based access provisioning (documented workflow; approval not tested in the lab)

- Access revocation

- Access validation

- Auditability and documentation



## 7. Evidence



Evidence is stored in:



`evidence/Mover-Department-Transfer/`



- `01-Mover-Finance-Group-Membership.png`

- `02-Mover-IT-Support-Group-Membership.png`

- `Evidence-Report.md`



## 8. Completion Criteria



The Mover process is considered complete when:



- The department or role change is documented.

- Required access is approved.

- New access is provisioned.

- Outdated access is revoked.

- Final access is validated.

- Evidence and execution details are documented.


