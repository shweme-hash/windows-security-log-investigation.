# Windows Security Log Investigation

**Beginner Blue-Team Lab | Windows 11 | Event Viewer**

## Overview
This mini-project documents a beginner investigation of Windows Security logs on a personal Windows 11 computer. The goal was to practice filtering events, reading logon records, and recording findings without making unsupported conclusions.

## Objectives
- Open Event Viewer and navigate to **Windows Logs → Security**.
- Filter for Event IDs **4624** and **4625**.
- Inspect a successful logon event.
- Identify **Logon Type 5** and understand it as a service logon.
- Record what was—and was not—observed.

## Tools
- Windows 11
- Event Viewer (`eventvwr.msc`)

## Method
1. Open Event Viewer.
2. Select **Windows Logs → Security**.
3. Use **Filter Current Log** and enter `4624,4625`.
4. Inspect a successful logon event (4624).
5. Review the event details and find the Logon Type.
6. Filter for `4625` separately and note whether results appear in the selected time range.

## Findings
- Event ID **4624** (successful logon) events were present in the selected time range.
- One inspected event involved the **SYSTEM** account and had **Logon Type 5**, which represents a service logon.
- No Event ID **4625** (failed logon) events were returned by the filter during the selected time range.

## Interpretation
The inspected service logon is consistent with normal Windows system activity. A service logon alone is not evidence of malicious activity.

No failed logons were observed in the filtered timeframe. This does **not** prove that failed logons never occurred; the observation is limited to the time range and logs examined.

## Screenshots
1. `screenshots/01-filtered-logon-events.jpg` — filtered Security log.
2. `screenshots/02-successful-logon-general.jpg` — successful logon event summary.
3. `screenshots/03-event-details-logon-type-5.jpg` — event details showing Logon Type 5.
4. `screenshots/04-logon-type-5-evidence.jpg` — close-up evidence of Logon Type 5, Logon Process (`Advapi`), and Authentication Package (`Negotiate`).



## Skills Practiced
- Event Viewer navigation
- Security-log filtering
- Event ID recognition
- Basic authentication-log analysis
- Distinguishing routine system activity from suspicious activity
- Evidence-based reporting

## Limitations
This is a beginner exercise on a personal Windows 11 machine. The review was limited to the selected time range and available local logs. It was not a full security audit.

## Safety & Privacy
This investigation was conducted on my own device. Machine-identifying details have been redacted from the included screenshots. Do not publish screenshots containing usernames, device names, email addresses, IP addresses, organisation information, or other private details.

## Next Steps
- Learn Event ID 4625 using a controlled test or sample logs.
- Investigate Event ID 4688 (process creation) when auditing is available.
- Practice documenting timelines and escalating suspicious events.
