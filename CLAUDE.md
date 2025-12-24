# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Ansible role (`docker`) for installing and configuring Docker on Ubuntu/Debian systems. It installs Docker CE with all plugins and configures syslog logging.

## Development Commands

### Linting
```bash
yamllint .                    # Lint all YAML files
ansible-lint                  # Lint Ansible code (currently disabled in CI)
```

### Pre-commit Hooks
```bash
pre-commit install            # Install hooks
pre-commit run --all-files    # Run all hooks manually
```

### Tool Management
Uses `mise` for tool versions (Ansible 13, pipx 1.8). Run `mise install` to set up.

## Role Structure

- `tasks/main.yml` - Installs Docker repo, packages, and configures daemon
- `handlers/main.yml` - Handler to restart Docker service
- `vars/main.yml` - Role variables (docker_users list)
- `meta/main.yml` - Role metadata and dependencies

## Required Variables

None required. The `docker_users` variable in `vars/main.yml` is available for optional user group configuration (requires uncommenting related tasks).

## YAML Style

Line length max 120, truthy values must be "true"/"false"/"yes"/"no", 1 space minimum after comments.
