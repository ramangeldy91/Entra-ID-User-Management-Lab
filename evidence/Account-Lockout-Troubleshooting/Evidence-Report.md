# Account Lockout Troubleshooting - Evidence Report



## 1. Overview



**Scenario:** Account Lockout Troubleshooting

**Environment:** Microsoft Entra ID (cloud-only test tenant)

**Test Account:** Password Reset Test User 01

**Employee ID:** LAB-USER-004

**Investigation Result:** No failed sign-in events identified



## 2. Investigation Performed



The following checks were performed in Microsoft Entra Admin Center:



1. Opened the test user's Sign-in Logs.

2. Checked the general tenant Sign-in Logs.

3. Inspected an available successful interactive administrative sign-in event.

4. Applied the `Failure` status filter.

5. Expanded the investigation period to the last 30 days.

6. Checked the Password Protection configuration page.

7. Rechecked the test account's enabled state.



## 3. Observations



| Check | Observation |

|---|---|

| General Sign-in Logs | Accessible |

| Test user's Sign-in Logs | No events found |

| Successful interactive sign-in | Available for the administrative account |

| Failed sign-in events | No results found |

| Failure filter, last 30 days | No results found |

| Password Protection configuration | Premium licensing notification displayed |

| Test account state | Enabled |



The inspected successful administrative sign-in showed `Status: Success`. Its authentication details included a single-factor authentication requirement and an additional detail indicating that the MFA requirement was satisfied by a claim in the token.



This event belonged to the administrative account, not the test account.



## 4. Safety Measures



- No repeated incorrect-password attempts were generated.

- No intentional account lockout was triggered.

- No security policies were modified.

- The test account remained enabled.



## 5. Validation Results



| Validation | Result |

|---|---|

| Sign-in Logs accessible | Passed |

| Available successful sign-in inspected | Passed |

| Failed sign-in search performed | Passed |

| 30-day investigation period checked | Passed |

| Test account enabled state verified | Passed |

| Actual lockout condition reproduced | Not tested |



## 6. Limitations



- No failed sign-in event was available for root-cause analysis.

- No actual Microsoft Entra Smart Lockout event was observed.

- Smart Lockout configuration values were not independently verified.

- Premium licensing restricted access to the requested Password Protection configuration.

- No on-premises Domain Controller was available.

- Event ID 4740 and AD DS account lockout properties were not tested against a live directory.

- No end-user sign-in recovery test was performed.



The on-premises AD DS troubleshooting procedure is documented in the workflow but was not executed in this lab.



## 7. Conclusion



The investigation confirmed that Microsoft Entra Sign-in Logs were accessible and that the test account remained enabled.



No failed sign-in events or actual account lockout conditions were identified during the investigation.



The lab demonstrates the initial diagnostic process and the distinction between cloud-based Microsoft Entra authentication and traditional on-premises AD DS account lockout troubleshooting.



It does not claim to demonstrate a successful recovery from an actual account lockout.
