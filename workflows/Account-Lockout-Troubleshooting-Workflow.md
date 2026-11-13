# Account Lockout Troubleshooting Workflow



## 1. Purpose



This workflow defines a structured process for investigating user sign-in problems, identifying account lockout conditions, restoring legitimate access, and documenting the resolution.



It covers two identity environments:



- Microsoft Entra ID (cloud identity).

- On-premises Active Directory Domain Services (AD DS).



These environments use different account protection and lockout mechanisms. Their diagnostic procedures must not be treated as interchangeable.



## 2. Scenario



**Request Type:** Account Lockout / Sign-in Failure

**Priority:** Based on business impact and number of affected users

**Environment:** Microsoft Entra ID (cloud-only test tenant), with a documented on-premises AD DS troubleshooting procedure.



A user reports that they cannot sign in to their corporate account.



Possible causes include:



- Incorrect or expired credentials.

- Account disabled by an administrator.

- Smart Lockout in Microsoft Entra ID.

- Account lockout in on-premises Active Directory.

- Cached credentials on another device or application.

- MFA or Conditional Access restrictions.

- Authentication issues involving applications or previously issued tokens.



## 3. Standard Operational Workflow



### Step 1 - Receive and Assess the Request



- Record the user's reported symptoms and the time the issue started.

- Identify the affected account and applications.

- Determine whether one user or multiple users are affected.

- Assess business impact and urgency.

- Check whether the issue started after a password change, device replacement, or account modification.



Do not ask the user to disclose their password.



### Step 2 - Verify the User Account



In Microsoft Entra ID:



- Locate the correct user account.

- Verify the account identity using available attributes.

- Check whether the account is enabled.

- Review relevant account and authentication information.



In on-premises AD DS:



- Locate the user in Active Directory.

- Check whether the account is enabled.

- Check whether the account is locked.

- Review account expiration and password-related properties.



### Step 3 - Investigate Microsoft Entra Sign-in Logs



Review the user's sign-in activity.



Check:



- Sign-in status.

- Sign-in error code.

- Failure reason.

- Additional details.

- Authentication requirement and authentication steps.

- Conditional Access results.

- Application and client information.

- Timestamp and correlation ID.



Differentiate between:



- Invalid credentials.

- Smart Lockout.

- Disabled account.

- MFA failure.

- Conditional Access denial.

- Other authentication or application errors.



Do not assume every failed sign-in indicates an account lockout.



### Step 4 - Investigate On-Premises AD DS Lockout



For environments using on-premises Active Directory:



Check the account's lockout state using authorized administrative tools.



Example PowerShell commands:



```powershell

Get-ADUser -Identity username -Properties LockedOut, badPwdCount, lockoutTime, Enabled

```



To identify account lockout events, review the Security event log on the relevant Domain Controllers.



**Event ID 4740 - A user account was locked out**



Review the event details, especially:



- Target account.

- Time of lockout.

- Caller Computer Name, when available.



The caller computer can help identify a device or service generating repeated authentication attempts.



### Step 5 - Identify the Root Cause



Investigate common sources of repeated authentication failures:



- Applications using an outdated stored password.

- Windows services running under the affected account.

- Scheduled tasks with outdated credentials.

- Persistent sessions on other devices.

- Mapped network drives.

- Mobile devices or email clients.

- Scripts or automation using outdated credentials.



Do not repeatedly attempt authentication with incorrect passwords as a diagnostic technique.



### Step 6 - Restore Access



Choose the corrective action based on the confirmed cause.



Possible actions include:



- Reset the password when authorized and necessary.

- Unlock an on-premises AD DS account when appropriate.

- Correct outdated credentials in services, scheduled tasks, or applications.

- Resolve MFA or Conditional Access issues through the appropriate support process.

- Escalate suspected compromised accounts to the security team.



Do not disable security controls simply to make the sign-in succeed.



### Step 7 - Validate Recovery



- Confirm that the account is in the expected state.

- Verify that the identified cause has been addressed.

- Ask the user to perform a controlled sign-in test.

- Confirm that the user can access the required service.

- Monitor for repeated failures when appropriate.



A successful administrative password reset alone does not prove that user authentication has been restored.



### Step 8 - Document and Close



Record:



- Reported symptoms.

- Investigation steps.

- Relevant error codes and event IDs.

- Identified root cause.

- Corrective actions.

- Validation results.

- Escalation details, if applicable.



Never include passwords, temporary credentials, or authentication secrets in the ticket or evidence.



## 4. Escalation Criteria



Escalate the incident when:



- Multiple users are unable to authenticate.

- A critical business application is affected.

- Repeated lockouts continue after the suspected cause is addressed.

- A privileged or administrative account is involved.

- There are indicators of credential compromise or suspicious authentication activity.

- The issue requires changes to identity security policies or infrastructure outside L1 authorization.



## 5. Lab Environment and Observations



The practical investigation was performed in a cloud-only Microsoft Entra ID test tenant.



Observed results:



- The general Sign-in Logs page was accessible.

- A successful interactive administrative sign-in was available for inspection.

- No failed sign-in events were found in the available 30-day period.

- The Password Protection configuration page indicated that Premium licensing was required for the requested configuration access.

- The test account remained enabled.

- No intentional repeated incorrect-password attempts were generated.



The on-premises AD DS investigation procedure is documented for technical reference. It was not executed against a live Domain Controller in this lab.



## 6. Technical Limitations



- No on-premises Active Directory Domain Controller was available.

- No real AD DS account lockout was generated.

- No Event ID 4740 was captured from a live Domain Controller.

- No actual Microsoft Entra Smart Lockout event was observed.

- Smart Lockout configuration values were not independently inspected.

- No end-user recovery test was performed as part of this scenario.



Microsoft Entra Smart Lockout and on-premises AD DS account lockout are separate mechanisms. Their logs, properties, and recovery procedures must be investigated in their respective environments.



## 7. Security Considerations



- Verify user identity before performing account recovery.

- Apply least privilege to administrative actions.

- Never request or disclose a user's existing password.

- Avoid repeated failed authentication attempts during troubleshooting.

- Investigate the source of repeated failures before repeatedly unlocking an account.

- Escalate suspected account compromise immediately.

- Preserve relevant audit and security logs.
