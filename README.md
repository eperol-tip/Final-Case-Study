# Final-Case-Study
This repository is for Final Case Study in CPE 028 - Developing Applications and Automation made by Elain Perol

## Network Automation using Ansible

## Network Topology
<img src="assets/network topology.png">

### Resources

*	1 PC with capability of running GNS3 and VirtualBox
*	VirtualBox
*	DEVASC Virtual Machine
*	GNS3
*	GNS3 VM

#### Configuration in DEVASC

##### SSH Config (`~/.ssh/config`)
```bash
Host *    
    Port 22
    User cisco
    StrictHostKeyChecking=no
    UserKnownHostsFile=/dev/null
    KexAlgorithms +diffie-hellman-group1-sha1
    Ciphers +3des-cbc
```
##### Netplan (`/etc/netplan/01-netcfg.yaml`)
```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    eth:
      match:
        name: en*
      dhcp4: yes
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.1.2/24
      gateway4: 192.168.1.1
```
```bash
$ sudo netplan apply
```

#### List of Playbooks
*	acl_config.yaml
*	backups_running-config.yaml
*	get_ipv4_config.yaml
*	iproute_config.yaml
*	ospf_config.yaml
*	playbook.yaml (master playbook)

