# Windows Security Log Investigation — Findings

**Objective:** Practice inspecting Windows Security logon events using Event Viewer.

## Observations
- Event ID 4624: successful logon events appeared in the selected period.
- An inspected event involved the SYSTEM account.
- Logon Type 5 was identified, which means a service logon.
- Event ID 4625: no results were returned in the selected timeframe.

## Assessment
The inspected service logon appears consistent with routine Windows activity. No failed logons were observed in the limited time range searched. These findings do not establish that the device is free of compromise.

## Limitations
This was a small beginner lab on a personal Windows 11 system. It was not a comprehensive security review.
