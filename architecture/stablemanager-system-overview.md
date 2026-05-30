# Stable Manager System Overview

## Purpose

Horse management application.

Primary functions:

- Daily horse notes
- Financial tracking
- Training records
- Healthcare records

## Business Requirement

Application must continue functioning when internet connectivity is unavailable.

## Known Components

### Mobile Application

Used by stable owners and staff.

### Backend API

Node.js application.

Managed by PM2.

### Web Layer

Nginx reverse proxy.

### Infrastructure

Hosted on Linux servers.

### Backups

Backup process exists but currently requires further investigation.

## Architectural Questions

- How many servers exist?
- Which services run on each server?
- What database is used?
- How is offline synchronization implemented?
- How are conflicts resolved?

- ## High-Level Architecture

Current understanding:

```text
Mobile App
    │
    ▼
Nginx
    │
    ▼
Node.js API (PM2)
    │
    ▼
Database

Backups
    │
    ▼
Backup Storage
```

Status:

⚠ Diagram is based on current understanding and requires verification.
```
## Information Sources

Current information has been obtained from:

- Server access observations
- PM2 process review
- Infrastructure investigation
- Discussions with application owner

This document will be updated as additional information is confirmed.
