# homelab-ansible-role-docker

Ansible role for installing and configuring Docker on Ubuntu/Debian systems.

## Requirements

- Ansible >= 2.15
- Target: Ubuntu (focal, jammy, noble) or Debian (bullseye, bookworm)

## Role Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `docker_users` | `["noxious"]` | List of users to add to the docker group (requires uncommenting tasks) |

## What Gets Installed

- Docker CE (Community Edition)
- Docker CLI
- containerd.io
- Docker Buildx plugin
- Docker Compose plugin
- Docker daemon configured with syslog logging

## Usage

### Install via requirements.yml

```yaml
- src: git@github.com:RobertYoung/homelab-ansible-role-docker.git
  scm: git
  version: main
  name: docker
```

```bash
ansible-galaxy install -r requirements.yml
```

### Example Playbook

```yaml
- hosts: servers
  roles:
    - role: docker
```

## License

MIT
