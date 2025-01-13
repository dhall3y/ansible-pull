## Overview

This repository contains the configuration and playbooks for automating the setup of my dev environments using Ansible.

## Prerequisites

- **git**
- **Ansible**
- **Python**
- **Python venv** (Optional)

## Usage

This will execute everything available
```bash
ansible-pull -U https://github.com/dhall3y/ansible-pull.git --vault-password-file ./vault.pass --ask-become-pass
```

The tag option can be used with valid tags to execute specific roles
```bash
ansible-pull -U https://github.com/dhall3y/ansible-pull.git --vault-password-file ./vault.pass --ask-become-pass --tags docker
```

In case of errors use the option `--vvv` to increase the logs verbosity
