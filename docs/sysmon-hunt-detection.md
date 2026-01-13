Goal
Detect suspicious PowerShell execution using Sysmon telemetry ingested into Wazuh.

Telemetry
Validated Sysmon ingestion in Wazuh using data.win.system.providerName:"Microsoft-Windows-Sysmon" and confirmed Process Create events (data.win.system.eventID:1).

Attack Simulation
Executed encoded PowerShell on the Windows endpoint to simulate living-off-the-land behavior:
powershell.exe -NoProfile -EncodedCommand ...

Detection (Hunt Query)
Detected the activity in Wazuh Security Events using:

data.win.system.providerName:"Microsoft-Windows-Sysmon"
AND data.win.system.eventID:1
AND data.win.eventdata.commandLine:*EncodedCommand*


Evidence Captured
Captured event context including image path, full command line, parent process, user, and timestamp.
