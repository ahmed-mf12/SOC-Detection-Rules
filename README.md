# SOC-Detection-Rules

Detection engineering repository containing Sigma rules for identifying common attacker techniques, mapped to the MITRE ATT&CK framework.

## Purpose

This repository documents detection logic I've developed to identify suspicious and malicious activity on Windows endpoints, based on techniques studied during my Blue Team / SOC Analyst training. Each rule follows the [Sigma](https://github.com/SigmaHQ/sigma) standard format, allowing it to be translated into SIEM-specific queries (Splunk SPL, QRadar AQL, etc.).

## Rules Overview

| Rule | MITRE ATT&CK Technique | Severity |
|---|---|---|
| [Windows Brute Force Login](sigma-rules/windows-bruteforce-login.yml) | T1110 - Brute Force | Medium |
| [PowerShell Encoded Command](sigma-rules/powershell-encoded-command.yml) | T1027 / T1059.001 | High |
| [Suspicious Scheduled Task](sigma-rules/suspicious-scheduled-task.yml) | T1053.005 - Persistence | Medium |
| [PsExec Lateral Movement](sigma-rules/psexec-lateral-movement.yml) | T1021.002 / T1570 | High |
| [LSASS Credential Dumping](sigma-rules/lsass-credential-dumping.yml) | T1003.001 | Critical |

## Methodology

Each rule includes:
- A clear description of the detected behavior
- MITRE ATT&CK technique mapping
- Documented false positive scenarios
- A severity level based on potential impact

## Tools & Format

- **Format:** Sigma (YAML)
- **Target log sources:** Windows Security & Sysmon event logs
- **Conversion targets:** Splunk SPL, QRadar AQL (via [Sigma converter tools](https://github.com/SigmaHQ/pySigma))

## Status

This is an actively growing collection developed as part of my Blue Team / SOC Analyst training. New rules are added as I study additional attacker techniques.
