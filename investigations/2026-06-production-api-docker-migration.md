# Production API Migration from PM2 to Docker

## Objective

Migrate a production Node.js API from a PM2-managed deployment to Docker while maintaining application availability.

## Initial State

Production architecture:

```text
Nginx
  ↓
PM2
  ↓
Node.js API
  ↓
PostgreSQL
```

Docker deployment had been prepared but was not yet serving production traffic.

## Step 1 - Container Deployment

Built Docker image and started container.

Commands used:

```bash
docker build -t api-image .
docker compose up -d
docker ps
docker logs <container>
```

Container started successfully.

However API requests immediately returned:

```json
{"error":"server_error"}
```

## Step 2 - Log Investigation

Reviewed container logs:

```bash
docker logs <container>
```

Observed:

```text
ECONNREFUSED
```

The application could not establish a connection to PostgreSQL.

## Investigation

Verified:

```bash
docker ps
systemctl status postgresql
free -h
df -h
```

Confirmed:

* Container was running
* PostgreSQL was running
* Sufficient memory available
* Sufficient disk space available

Resource exhaustion was ruled out.

## Step 3 - Hypothesis Testing

Suspected networking issue.

Container was temporarily started using host networking:

```bash
docker run --network host ...
```

Result:

Application connected successfully.

This confirmed the problem was related to Docker-to-PostgreSQL networking.

## Step 4 - PostgreSQL Access Review

Reviewed PostgreSQL configuration.

Investigated:

```bash
cat postgresql.conf
cat pg_hba.conf
```

Observed that PostgreSQL had previously been hardened and was accepting only local connections.

This configuration prevented Docker containers from connecting through the container network.

## Step 5 - Solution

Configured PostgreSQL to accept connections from the internal Docker network only.

Security objectives:

* Keep public database access disabled
* Allow Docker connectivity
* Restrict access to internal network scope

## Step 6 - Validation

After PostgreSQL reload:

```bash
sudo systemctl restart postgresql
```

Verified:

```bash
docker logs <container>
curl http://localhost:<port>/api/...
```

Application successfully returned data from PostgreSQL.

## Step 7 - Nginx Traffic Switch

Reviewed Nginx configuration:

```bash
sudo nginx -t
```

Updated upstream target from PM2 deployment to Docker deployment.

Reloaded Nginx:

```bash
sudo systemctl reload nginx
```

## Step 8 - Production Verification

Stopped PM2 application:

```bash
pm2 stop <application>
pm2 list
```

Production API continued operating correctly.

This confirmed traffic was now served exclusively by Docker.

## Step 9 - Reboot Validation

Performed reboot test:

```bash
sudo reboot
```

After restart:

```bash
docker ps
curl https://production-endpoint/...
```

Container restarted automatically and application remained available.

## Lessons Learned

* Docker localhost is not the same as host localhost.
* Database hardening can affect containerized workloads.
* Logs are often the fastest path to root cause analysis.
* Every production migration should include rollback planning.
* Reboot testing is an important part of deployment validation.

## Outcome

Successfully migrated production traffic from PM2 to Docker while preserving database security and maintaining service availability.
