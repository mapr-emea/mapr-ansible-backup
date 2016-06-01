# This a collection of Ansible scripts

Ansible 2.1 or higher required!

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

If you want to enable native security after successful installation goto /group_vars/all and add
the cluster name you used in UI installation (only required for secured cluster) and run

```
ansible-playbook -i hosts_run-installer-template site-run-installer-nativesecurity.yml
```

## Install unsecure cluster

Use `hosts_template` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template site-unsecure.yml
```

## Install cluster with native security

Use `hosts_template` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template site-nativesecurity.yml
```

## Helpers

Helpers are located in the `helper` folder.

### Create several users to test ACE

This document contains the ACE file/Volume demo: https://docs.google.com/document/d/11DkezjtZcwVdXtrfBU3eBnNNObakILyYVJmyaKHdUHs/edit#heading=h.v7cls48r0iz7
To create the users and groups just run:

Run:

```
ansible-playbook -i hosts_template helper/create-user-ace.yml
```


## Other notes for copying

export ANSIBLE_HOSTS=/Users/chufe/Documents/workspaces/mapr_ansible/hosts
