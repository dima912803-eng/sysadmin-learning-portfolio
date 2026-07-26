# Infrastructure Investigations

This section contains real-world infrastructure projects, troubleshooting investigations, security improvements and production change documentation.

The reports focus on practical engineering decisions, validation and operational outcomes rather than step-by-step tutorials.

## Case Study Index

| Case Study                                                                        | Category               | Technologies                       | Key Skills                                                |
| --------------------------------------------------------------------------------- | ---------------------- | ---------------------------------- | --------------------------------------------------------- |
| [Building a Reliable CI Pipeline](./CASE-01-CI-PIPELINE.md)                       | CI/CD                  | GitHub Actions, Docker, Node.js    | Continuous Integration, Build Validation, Automation      |
| [Controlled Production Deployment](./CASE-02-CONTROLLED-CD.md)                    | CI/CD                  | GitHub Actions, Docker, Linux, SSH | Deployment Automation, Release Control, Change Management |
| [Linux Infrastructure Reorganisation](./CASE-03-INFRASTRUCTURE-REORGANISATION.md) | Infrastructure         | Linux, Docker, Git                 | Filesystem Design, Permissions, Maintainability           |
| Production API Docker Migration                                                   | Infrastructure         | Docker, Nginx, PostgreSQL          | Migration, Rollback, Troubleshooting                      |
| PostgreSQL Exposure Remediation                                                   | Security               | PostgreSQL, Linux                  | Database Hardening, Risk Assessment                       |
| Secure Docker–PostgreSQL Connectivity                                             | Security               | Docker, PostgreSQL                 | Network Access Control, Troubleshooting                   |
| SSH Hardening and Fail2Ban Deployment                                             | Security               | Linux, SSH, Fail2Ban               | Access Control, Brute-Force Protection                    |
| Ubuntu Server Hardening and Monitoring Cleanup                                    | Security / Operations  | Ubuntu, Linux                      | Hardening, Monitoring, Maintenance                        |
| Production Monitoring Incident Investigation                                      | Monitoring             | Linux, Monitoring Tools            | Incident Investigation, Root-Cause Analysis               |
| CPU Usage Investigation                                                           | Monitoring             | Linux, Docker                      | Performance Analysis, Troubleshooting                     |
| Backup Strategy Review                                                            | Operations             | PostgreSQL, Linux                  | Backup Validation, Disaster Recovery                      |
| Disk Space Remediation                                                            | Operations             | Linux, journald, Log Rotation      | Capacity Management, Log Management                       |
| PM2 Process Review                                                                | Application Operations | PM2, Node.js, Linux                | Process Investigation, Service Management                 |
| Production Database Migration                                                     | Database Operations    | PostgreSQL                         | Migration Planning, Validation, Recovery                  |
| First Server Access                                                               | Administration         | Linux, SSH                         | Discovery, Initial Assessment                             |

## Documentation Approach

Each report uses the structure most appropriate for the work performed.

Troubleshooting investigations generally include:

* Problem or operational risk
* Investigation and evidence
* Root cause
* Resolution
* Validation
* Lessons learned

Infrastructure projects generally include:

* Initial situation
* Engineering challenge
* Design decisions
* Implementation approach
* Architecture diagram, where useful
* Outcome and skills demonstrated

Sensitive infrastructure details such as credentials, addresses, internal endpoints and customer information are intentionally excluded.
