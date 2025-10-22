# deploy.sh - POSIX Idempotent Deployment Script

This repository contains a POSIX-compliant, idempotent shell script `deploy.sh` that:
- Clones or updates a Git repo (HTTPS with PAT),
- Syncs project files to a remote Ubuntu/Debian server via `rsync`/`ssh`,
- Installs Docker / docker-compose / nginx on the remote host (apt-based),
- Builds and runs the app (supports `Dockerfile` or `docker-compose.yml`),
- Configures Nginx as a reverse proxy,
- Validates deployment and logs output to `deploy_YYYYMMDD_HHMMSS.log`.

## Requirements (local)
- `sh` (POSIX shell)
- `git`
- `rsync`
- `ssh`
- `sed` (for small path normalization)
- Internet access for cloning

## Requirements (remote)
- apt-based Linux (Debian/Ubuntu) recommended
- `ssh` access with private key
- `sudo` privileges for installing packages and reloading services

## Usage
```sh
chmod +x deploy.sh
./deploy.sh

