# 📊 Findings & Reflections: Splunk Security Monitoring Homelab

# 🔍 Overview
This homelab explored how to use Splunk for structured security log analysis and event-based alerting with Windows Security Event Logs. The core objective was to simulate common SOC (Security Operations Center) workflows by importing .log files, filtering key Event IDs, and building alert logic that identifies high-risk security activity such as failed logins, privileged access, and log clearing.

Rather than relying on live log ingestion, this project demonstrated that static event datasets can still power detection logic and alert simulation effectively through Splunk’s built-in tools.

# 🔧 What I Did
1. Imported sample .log files into Splunk Free and created a custom index (splunk_homelab).

2. Parsed structured security event logs using spath to extract fields like EventID, user, and src_ip.

3. Focused on filtering and analyzing high-value Windows Event IDs:

4624 – Successful Logons

4625 – Failed Logons

4672 – Privileged Logons

1102 – Log Clearing (audit trail tampering)

4. Developed a Splunk alert that simulates brute force detection by monitoring Event ID 4625 activity.

5. Used “Add to Triggered Alerts” as the alert action to validate detection logic directly within the Splunk interface.

6. Created Markdown-based documentation for queries, alerts, findings, and relevance to SOC workflows.

# 🔎 Key Findings
Filtering for individual Event IDs allows SOC analysts to quickly pinpoint critical activity such as failed logins, user privilege changes, or evidence tampering.

“Add to Triggered Alerts” is an effective method for confirming that scheduled alerts fire correctly—especially when working in a static data environment where email delivery isn’t necessary.

Creating and managing cron schedules (e.g., */15 * * * *) combined with proper time range windows ensures Splunk continuously evaluates static logs.

Mastering spath, stats, and event filtering lays a strong foundation for more advanced detection engineering with correlation rules and dashboards.

The project reinforces the importance of data normalization and field consistency when ingesting non-live log sources.

# 🛡️ SOC Skills Demonstrated
Log Parsing & Field Extraction

SIEM Query Building for Indicators of Compromise

Alert Logic Design & Scheduling

Privilege Escalation & Authentication Monitoring

Security Event Investigation using known MITRE-aligned behaviors

Operational Documentation using Markdown for professional storytelling

# 🌐 Real-World Relevance
This homelab simulates daily tasks of a Tier 1–2 SOC analyst, where large volumes of event logs must be triaged for signals of attack. The workflows of querying logs, detecting failed logins, isolating privilege escalations, and triggering alerts all map to active duties in enterprise security teams.

By mastering these flows with static data and turning it into a repeatable process, you're proving not just technical skill—but the process-oriented mindset that SOCs rely on to manage real threats at scale.
