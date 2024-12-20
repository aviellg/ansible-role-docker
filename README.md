# Ansible Role: Docker

This Ansible role installs and configures Docker and Docker Compose on target hosts. It also sets up necessary directories and permissions for Docker management.

## Requirements

- Ansible 2.9 or later
- Supported platforms: Ubuntu/Debian

## Role Variables

Define the following variables in `group_vars/all/vars.yml`:

```yaml
# Docker Role Variables
bootstrap_admin_user: autoadmin
docker_root_folder: "/home/{{ bootstrap_admin_user }}/docker"
PUID: 1000
PGID: 1000
TZ: "Europe/Zurich"
USERDIR: "/home/{{ bootstrap_admin_user }}"
DOCKERDIR: "/home/{{ bootstrap_admin_user }}/docker"
DATADIR: "/media/storage"
HOSTNAME: "udms"
```


## Tasks Overview
Install Docker and Docker Compose: Installs Docker and Docker Compose packages.

User Group Configuration: Adds the specified user to the Docker group.

Directory Setup: Creates essential directories for Docker operations:

Docker root directory

Appdata directory

Compose directory

Logs directory

Scripts directory

Secrets directory with permissions

Shared directory

Environment File Setup: Creates and populates a .env file with necessary environment variables.

Docker Compose Configuration: Creates a master Docker Compose file.

Permissions and ACLs: Installs ACL, sets permissions, and configures ACLs for the Docker root folder.
