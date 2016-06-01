# This a collection of Ansible scripts

## Supported OS

* Redhat
* CentOS

## Use the UI installer

This script sets up the Java, mapr user with password `mapr123`, install ntp and rpcbind. Last step is that it launches the MapR-UI installer on the master-node.
Use `hosts_run-installer-template` as template and copy it.

Execute:

```
ansible-playbook -i hosts_run-installer-template site-run-installer.yml
```

Goto `https://<masternode>:9443` and login with mapr and password mapr123.
Click wizard and install.

If you want to enable native security after successful installation run:

```
ansible-playbook -i hosts_run-installer-template site-run-installer-nativesecurity.yml
```

export ANSIBLE_HOSTS=/Users/chufe/Documents/workspaces/mapr_ansible/hosts
