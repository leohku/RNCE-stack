# RNCE Stack

RNCE Stack (pronounced "rinse") is an unopinionated template for building and quickly deploying web applications running on a single machine.

## Features
- GitHub Actions pipeline to deploy on any bare-metal machine or VM, even behind firewalls / VPNs
- Fully containerized setup, spin up a working local app by running `yarn local:start`
- Uses Typescript, React SPAs, and Express.js by default, unopinionated otherwise

## Customization
Find and replace `dashboard` in the project repository to customize to your project name and domain.

## Requirements of remote deployment machine
- Key based SSH is enabled
- Tailscale is enabled and reachable by GitHub Runner (non-blocking ACL rules)
- Docker is enabled, user account is in `docker` group (no `sudo` to run containers)

**Note:** Having Docker rootless mode configured in remote SSH account's `.bashrc` is not recommended as containers deployed with this template uses Docker's "rootful" default mode. This can cause confusion as running `docker container ls` will return an empty list in SSH when in fact the container is running in "rootful" mode.
