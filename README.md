# Linux Server Toolkit

A practical collection of Linux administration, deployment, monitoring, backup, and service-management examples.

This repository is designed as a portfolio project showing hands-on experience with Ubuntu/Linux servers, Bash scripting, systemd, MySQL backups, application deployment, log inspection, and basic health monitoring.

## Features

- Server health checks
- Disk and memory monitoring
- Process and service checks
- Application deployment helper
- MySQL database backups
- Rotating local backups
- systemd service templates
- Log inspection helpers
- Environment-based configuration
- Safe shell scripting practices

## Project Structure

```text
Linux-Server-Toolkit/
├── scripts/
│   ├── backup-mysql.sh
│   ├── deploy-node-app.sh
│   ├── health-check.sh
│   ├── service-status.sh
│   └── rotate-backups.sh
├── systemd/
│   └── node-app.service.example
├── docs/
│   └── server-checklist.md
├── .env.example
├── .gitignore
└── README.md
```

## Requirements

- Linux / Ubuntu
- Bash
- systemd
- MySQL or MariaDB for database backup examples
- Node.js for the deployment example

## Quick Start

Make scripts executable:

```bash
chmod +x scripts/*.sh
```

Copy the example environment file:

```bash
cp .env.example .env
```

Edit the values for your server before using deployment or backup scripts.

## Server Health Check

```bash
./scripts/health-check.sh
```

Reports:

- Hostname
- Kernel
- Uptime
- CPU load
- Memory use
- Disk use
- Network addresses
- Failed systemd services

## Service Status

```bash
./scripts/service-status.sh nginx mysql
```

You can pass one or more systemd service names.

## MySQL Backup

```bash
./scripts/backup-mysql.sh
```

Database credentials are read from environment variables.

For production systems, prefer MySQL option files, secret managers, or another secure credential mechanism rather than storing passwords directly in shell history.

## Node.js Deployment Example

```bash
./scripts/deploy-node-app.sh
```

The deployment helper demonstrates a common workflow:

1. Enter application directory
2. Pull the configured Git branch
3. Install production dependencies
4. Restart the configured systemd service
5. Display service status

## systemd

`systemd/node-app.service.example` contains a reusable service template for Node.js applications.

Copy it to:

```text
/etc/systemd/system/my-app.service
```

Then run:

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now my-app
```

## Technology

- Linux / Ubuntu
- Bash
- systemd
- MySQL
- Node.js
- Git
- SSH-style deployment workflows

## Safety

These scripts are examples and intentionally avoid destructive automation.

Review every script and configure paths, users, database names, and service names before using it on a production server.

## Author

**William Murphy / CraftEarth**

GitHub: https://github.com/CraftEarth
