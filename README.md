# TechNova IT Support — Ticket #1044

## Windows 11 — Event Viewer & Activation Troubleshooting

**Ticket Status:** Pending / Escalated  
**Priority:** Medium  
**Category:** Windows Troubleshooting / Software Licensing  
**Environment:** Windows 11 Pro — PC01  
**Lab Type:** Simulated IT Support Incident

---

## 1. Incident Description

An employee named Carlos reported that his Windows 11 workstation was experiencing errors and unexpected application behavior.

The IT Support team was assigned to investigate Windows event logs and identify potential system issues.

During the investigation, a Windows activation error was discovered.

**Objective:** Investigate a real Windows event, verify the system's activation status, perform authorized troubleshooting, and document the findings and escalation requirements.

## 2. Lab Environment

| Component | Configuration |
|---|---|
| Company | TechNova Solutions (Simulated) |
| Workstation | PC01 |
| Operating System | Windows 11 Pro |
| Virtualization | VMware Workstation |
| Primary Diagnostic Tool | Windows Event Viewer |
| Additional Tools | PowerShell, Windows Activation Settings |
| User Account | Local Administrator |

## 3. Initial Investigation — Event Viewer

Opened Windows Event Viewer using:

`eventvwr.msc`

Navigated to:

**Windows Logs → Application**

Filtered the Application log to display Critical and Error events.

Identified the following event:

| Property | Result |
|---|---|
| Event ID | 8198 |
| Source | Security-SPP |
| Level | Error |
| Application | slui.exe |
| Error Code | 0x8007139F |

The event indicated that a Windows license activation operation had failed.

This finding prompted a separate investigation into the workstation's activation status.

## 4. PowerShell Licensing Diagnostics

### Step 1 — Check Activation Expiration

Executed:

`slmgr /xpr`

**Result:** Windows was operating in Notification mode.

This indicated that Windows did not currently have a valid activated status.

### Step 2 — Review Detailed Licensing Information

Executed:

`slmgr /dlv`

Observed the following:

| Property | Result |
|---|---|
| Windows Edition | Windows 11 Pro |
| License Channel | Retail |
| License Status | Notification |
| Notification Reason | 0xC004F034 |

The licensing information confirmed that the workstation was not activated.

## 5. Windows Activation Settings Verification

Opened:

**Settings → System → Activation**

Observed:

- Activation State: Not active
- Error Code: 0xC004F213
- Windows reported that no product key was found on the device.

This provided additional evidence that Windows activation had not been completed successfully.

The different error codes were documented separately rather than assumed to have identical causes.

## 6. Windows Activation Troubleshooter

Executed the built-in Windows Activation Troubleshooter.

**Result:**

The troubleshooter completed but was unable to activate Windows.

The tool recommended obtaining assistance or using a genuine Windows license.

No unauthorized product keys, activation bypasses, or licensing modifications were attempted.

## 7. Findings and Root Cause Assessment

The investigation confirmed that Windows 11 Pro was not activated.

The system reported that no product key was found, and the licensing service indicated Notification status.

The Event ID 8198 activation failure was consistent with the broader licensing issue, although its exact underlying cause was not independently established.

**Confirmed Finding:** Windows activation is incomplete.

**Unresolved Dependency:** Verification of a valid product license or digital entitlement.

**Scope Limitation:** The original report of unexpected application behavior was not independently reproduced or diagnosed. The activation issue was identified during event-log investigation and should not automatically be considered the cause of application crashes.

## 8. Escalation and Recommended Next Steps

In a real enterprise environment, the IT Support technician should:

1. Verify whether the workstation has a valid Windows license or digital entitlement.
2. Confirm that the installed Windows edition matches the assigned license.
3. Contact the organization's licensing administrator or authorized IT team.
4. Perform activation only through approved licensing procedures.
5. Verify the activation state after an authorized resolution.
6. Continue investigating the original application issue separately if it persists.

## 9. Ticket Status

**Status: Pending / Escalated**

The diagnostic investigation was completed successfully, but Windows remains unactivated.

The case requires licensing verification and an authorized activation method.

The ticket must not be marked Resolved until the relevant issue has been corrected and verified.

## 10. Screenshots and Evidence


## 10. Screenshots and Evidence

### 1. Event Viewer — Error 8198
![Event Viewer Error 8198](event%20view/01-event-viewer-error-8198.png)

### 2. Windows Licensing Details
![Windows Licensing Details](event%20view/02-license-details.png)

### 3. PowerShell Activation Status
![PowerShell Activation Status](event%20view/03-activation-status-powershell.png)

### 4. Windows Activation Error
![Windows Activation Error](event%20view/04-windows-activation-error.png)

### 5. Activation Troubleshooter Result
![Activation Troubleshooter Failed](event%20view/05-activation-troubleshooter-failed.png)
  

## 11. Technical Skills Demonstrated

- Windows 11 troubleshooting
- Windows Event Viewer analysis
- Event ID and source identification
- PowerShell and Windows licensing commands
- Software activation diagnostics
- Windows Settings administration
- Root cause assessment
- Incident documentation
- IT ticket escalation procedures
- Evidence-based troubleshooting

## 12. Lessons Learned

Windows Event Viewer can reveal system issues that are not immediately obvious to the user.

Multiple diagnostic tools should be used to validate findings.

An observed error should not automatically be assumed to explain an unrelated symptom.

IT Support technicians must distinguish between a completed diagnosis and a fully resolved incident.

Licensing issues should be addressed through authorized organizational procedures.

---

**TechNova Solutions — Hands-on IT Support Portfolio**  
**Ticket #1044 | Event Viewer & Windows Activation Troubleshooting**
