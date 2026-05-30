# PM2 Process Review

## Objective

Understand how the Stable Manager backend application is managed and kept running in production.

## Background

The backend application is a Node.js service.

A process manager is required to:

- Start the application
- Restart the application if it crashes
- Manage logs
- Run multiple processes

## Technology Investigated

PM2

## Activities Performed

Commands reviewed:

```bash
pm2 list
pm2 show <process>
pm2 logs
```

## Findings

PM2 acts as a supervisor for Node.js applications.

Key capabilities:

- Automatic restart after failure
- Process monitoring
- Log management
- Startup on server reboot

## Why This Matters

Without a process manager:

- Application could stop unexpectedly
- Manual intervention would be required
- Service availability would be reduced

## Lessons Learned

Application uptime depends not only on application code but also on supporting infrastructure components such as process managers.

## Next Questions

- How is deployment performed?
- How are PM2 configurations stored?
- How are logs rotated?
