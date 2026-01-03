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

By default the dotfiles will also be installed --skip-tags can be used to skip the install of all dotfiles or specific one

```bash
ansible-playbook local.yml -i localhost -c local --vault-password-file ../vault.pass --ask-become-pass --skip-tags dotfiles
```

```bash
ansible-playbook local.yml -i localhost -c local --vault-password-file ../vault.pass --ask-become-pass --skip-tags zsh_dotfiles
```

This can be used in conjuction with --tags:

```bash
# this will install zsh and nvim. Nvim dotfiles will be installed while the one for zsh will be skipped
ansible-playbook local.yml -i localhost -c local --vault-password-file ../vault.pass --ask-become-pass --tags zsh,nvim --skip-tags zsh_dotfiles
```

In case of errors use the option `--vvv` to increase the logs verbosity

## Tests

A Dockerfile and docker-compose is present to help with testing in a clean environment.

Once started ansible-pull command can be used or if a volume is mounted ansible-playbook can be used

Example:
```bash
ansible-playbook local.yml -i localhost -c local --vault-password-file ../vault.pass --ask-become-pass
```
