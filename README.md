# Greenfield Kubernetes

Creates a local Kubernetes cluster. Launches three VMs using VirtualBox. Then bootstraps those with an Ansible playbook

## Requirements

1. Ansible installed
2. VirtualBox Installed
3. Vagrant installed

## Run the applications

1. Clone the repository
2. CD into the project directory
3. Run `vagrant up`

## Cleanup

1. In the directory of the project, run `vagrant destroy -f`
2. The -f will prevent prompts

## System Requirements

- 8GB RAM or greater. This will create 3 VMs each with 2GB

## Subsystem Linux

I ran this using WSL Ubuntu. Some caveats to consider if you do the same

- https://www.vagrantup.com/docs/other/wsl.html#vagrant_wsl_windows_access_user_home_path
- Vagrant has to be installed on both WSL and windows. The versions of both need to match.
- Vagrant will need to use sudo to write with local_action. This requires that you've sudoed at least once in the terminal you're running from
- You may have issues with the wrong permissions on an ssh key that's generated. When you try to `chmod 600` the file, it won't change the permissions. You'll need to add the following entry to WSL and then restart it.

`/etc/wsl.conf`

```
[automount]
options = "metadata"
```
