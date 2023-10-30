# Nyameri Codespace♥️ Jupyter Notebook

Welcome to my shiny new codespace! I got everything fired up and running for you to explore Python and Jupyter notebooks.

# AI XDR iSensor Playbook for Tactical Threat Intelligence

## Objective
The objective of this playbook is to provide tactical threat intelligence to security teams by automating repetitive tasks associated with Cortex XDR incidents.

## Dependencies
This playbook uses the following sub-playbooks, integrations, and scripts:
- Palo Alto Networks Cortex XDR - Investigation and Response
- Recorded Future v2

## Playbook Inputs
| Name | Description | Default Value | Required |
| --- | --- | --- | --- |
| CVE | CVE ID to check if it is related to the C2 context. | | Optional |
| IP | IP Address to check if it is related to the C2 context. | | Optional |
| Context | Context to use for assessment. This is used by Recorded Future to calculate the relevant score and verdict. Valid values are "c2", "malware" and "phishing". | phishing | Required |

## Playbook Outputs
| Path | Description | Type |
| --- | --- | --- |
| DBotScore.Indicator | The indicator that was tested | string |
| DBotScore.Type | Indicator type | string |
| DBotScore.Vendor | Vendor used to calculate the score | string |
| DBotScore.Score | The actual score | number |
| File.SHA256 | File SHA-256 | string |
| File.SHA512 | File SHA-512 | string |
| File.SHA1 | File SHA-1 | string |
| File.MD5 | File MD5 | string |
| File.CRC32 | File CRC32 | string |
| File.CTPH | File CTPH | string |
| IP.Address | IP address | string |
| IP.ASN | ASN | string |
| IP.Geo.Country | IP Geolocation Country | string |
| Domain.Name | Domain name | string |
| URL.Data | URL name | string |
| CVE.ID | CVE ID | string |

## Steps
1. Fetch a Palo Alto Networks Cortex XDR incident.
2. Sync and update new XDR alerts that construct the incident.
3. Trigger a sub-playbook to handle each alert by type.
4. Perform enrichment on the incident's indicators and hunting for related IOCs.
5. Based on the severity, let the analyst decide whether to continue to the remediation stage or close the investigation as a false positive.

## Conclusion
This playbook helps security teams save time and keep their incidents in sync with Cortex XDR. It also automates repetitive tasks associated with Cortex XDR incidents, providing tactical threat intelligence to security teams.
