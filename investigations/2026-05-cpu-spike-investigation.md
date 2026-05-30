# CPU Spike Investigation

## Objective

Investigate increased CPU utilization on a production Linux server.

## Environment

- Linux Server
- Node.js Application
- PM2
- Nginx

## Symptoms

Observed periods of elevated CPU utilization.

## Investigation Activities

Reviewed:

- Running processes
- PM2 services
- Application logs
- System resource usage

Tools used:

```bash
top
ps aux
pm2 list
pm2 logs
```

## Findings

High CPU utilization can originate from:

- Application code
- Background jobs
- Database queries
- External requests
- System maintenance tasks

Further investigation is required to identify the exact source.

## Lessons Learned

CPU spikes should be investigated systematically.

Monitoring processes, logs, and application behavior together provides better visibility than reviewing only one source.

## Next Steps

- Review application logs during spikes
- Identify recurring patterns
- Implement monitoring and alerting
