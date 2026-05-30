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
