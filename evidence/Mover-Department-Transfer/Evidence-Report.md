# Evidence Report - Mover Department Transfer



## 1. Test Overview



**Project:** Entra ID User Management Lab

**Platform:** Microsoft Entra ID

**Test Type:** Department Transfer / Group Membership Management

**Test Identity:** IAM Lab User 01

**Employee ID:** LAB-USER-001

**Test Result:** PASS



## 2. Test Objective



Verify that an employee's security group memberships can be updated during a department transfer.



The test checks that:



\- The employee is added to the required Finance security group.

\- The employee is removed from the previous IT Support security group.

\- The final group membership reflects the target department.



## 3. Initial State



Before the transfer, the test user was a member of:



\- `GRP-IT-Support-Basic`



The target group was:



\- `GRP-Finance-Basic`



## 4. Actions Performed



1\. Created the `GRP-Finance-Basic` security group.

2\. Added `IAM Lab User 01` to the Finance group.

3\. Verified that the user belonged to both groups during the transition.

4\. Removed the user from the IT Support group.

5\. Verified the final group membership.



## 5. Validation Results



| Validation | Expected Result | Actual Result | Status |

|---|---|---|---|

| Finance group membership | Present | Present | PASS |

| IT Support group membership | Absent | Absent | PASS |

| Final department group membership | Finance only | Finance only | PASS |



**Overall Result: PASS - 3 of 3 validation checks successful.**



## 6. Audit Log Evidence

Microsoft Entra Audit Logs were reviewed to verify the administrative group membership changes.

The following activities were confirmed:

- Add member to group - GRP-Finance-Basic
- Remove member from group - GRP-IT-Support-Basic

These events provide an audit trail for the access changes performed during the department transfer.



## 7. Evidence Files



### Evidence 01 - Finance Group Membership



**File:** `01-Mover-Finance-Group-Membership.png`



Shows `IAM Lab User 01` as a member of `GRP-Finance-Basic`.



### Evidence 02 - IT Support Group Membership



**File:** `02-Mover-IT-Support-Group-Membership.png`



Shows that `IAM Lab User 01` is no longer a member of `GRP-IT-Support-Basic`.



## 8. Security Considerations



\- Group membership was used to demonstrate role-based access management.

\- New group membership was verified before removing the previous membership.

\- The test follows the principle of Least Privilege.

\- Group membership does not independently prove access to an application or resource.



## 9. Scope and Limitations



This was a controlled laboratory exercise using a cloud-only Microsoft Entra ID test account.



The following activities were not performed:



\- HR request submission

\- Manager or resource-owner approval

\- Actual Finance application access testing

\- Verification of resource-level permissions



These steps belong to the designed Mover workflow but are not claimed as completed operations.



## 10. Conclusion



The department transfer group-membership test completed successfully.



The test user was added to the Finance security group and removed from the IT Support security group. The final membership was verified in Microsoft Entra ID.



The evidence supports the group membership changes performed during this laboratory exercise.


