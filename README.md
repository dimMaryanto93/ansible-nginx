## Ansible - User Guide

Persiapan yang harus di lalukan, diantaranya

1. Create new user on your server, Recomend using **very-very Strong Password** or using password generator.  

    ```bash
    adduser <username>
    ```

2. Granted to sudoers with NOPASSWD, using `visudo`
    ```ini
    username    ALL=(ALL) NOPASSWD:ALL
    ```

3. Authenticate with private-key for login ssh, generate ssh key on your local machine then use `ssh-copy-id user@your-ip-server` to copy public key to your server.

### Using Ansible Playbooks

This is ansible for installing Kubernetes cluster with dockershim as container runtime, currently support for 

- CentOS 
- Ubuntu

This page show you step-step installing docker using Ansible. First install requirement using command:

```bash
ansible-galaxy collection install -r requirements.yaml
```

- Update your environment variables in `group_vars/all.yaml.example` then rename to `group_vars/all.yaml`

- Install package and do stuff

```bash
ansible-playbook -i hosts.ini site.yaml
```