# This is a collection of Ansible scripts

Ansible 2.1 or higher required!

## Supported OS

* Redhat 7 or higher
* CentOS 7 or higher
* Ubuntu 14.x or higher
* Suse SLES 12 or higher

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

## Inventory file templates

Can be found `host_templates`

## Install cluster

Use `host_templates/hosts_cluster` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template site-cluster.yml
```

## Install client

Use `host_templates/hosts_client` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template site-client.yml
```

## Install RStudio Server (m5 license requried for NFS)

Use `hosts_template` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template rstudio-server.yml
```

## Install Zeppelin

Use `hosts_template` as template and copy it and the hostnames to the components you want to get installed. If components are not required, just leave the block empty. Then run:

```
ansible-playbook -i hosts_template site-zeppelin.yml
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


/opt/mapr/server/configure.sh -N maprpoc.arvato.com -Z ip-172-19-0-250.eu-central-1.compute.internal,ip-172-19-0-251.eu-central-1.compute.internal,ip-172-19-0-252.eu-central-1.compute.internal -C ip-172-19-0-250.eu-central-1.compute.internal:7222,ip-172-19-0-251.eu-central-1.compute.internal:7222,ip-172-19-0-252.eu-central-1.compute.internal:7222 -u mapr -g mapr -unsecure -RM ip-172-19-0-253.eu-central-1.compute.internal,ip-172-19-0-254.eu-central-1.compute.internal -HS ip-172-19-0-251.eu-central-1.compute.internal
