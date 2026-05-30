# System Inventory

## Stable Manager Environment

### Servers

| Server | Purpose | Status | Notes |
|----------|----------|----------|----------|
| Server 1 | Unknown | Active | Requires investigation |
| Server 2 | Unknown | Active | Requires investigation |

---

## Operating Systems

| Component | Technology |
|------------|------------|
| Production Server | Linux |

---

## Web Layer

| Component | Technology |
|------------|------------|
| Reverse Proxy | Nginx |

---

## Application Layer

| Component | Technology |
|------------|------------|
| Backend API | Node.js |
| Process Manager | PM2 |

---

## Database

Status: Unknown

Questions:

- Which database is used?
- Where is it hosted?
- How are backups performed?

---

## Monitoring

Status: Unknown

Questions:

- Are alerts configured?
- Is uptime monitored?
- Is resource usage monitored?

---

## Backup

Status: Partially Known

Known:

- Backup process exists

Unknown:

- Frequency
- Retention
- Restore testing

---

## Open Questions

1. How many production servers exist?
2. What database is used?
3. How is synchronization implemented?
4. How are deployments performed?
5. How are backups verified?
