# POC Ansible Playbook and roles for Postgresql Setup

This POC use Vagrant to provision VMs, and use `ansible-playbook` command to execute provisioning

## Prerequisite
- VirtualBox
- Vagrant
- Python3 
- Python3 Venv
- Ansible

## Setup
### Linux and MacOS
- Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads), required by Vagrant.
- Install [Vagrant](https://www.vagrantup.com/downloads.html).
- Python3 included.
- Venv included in Python3.
- Create directory to store virtual environment `mkdir -p ~/.venv/ansible`. 
- Create virtual environment `python3 -m venv ansible ~/.venv/ansible`
- Activate virtual environment `source ~/.venv/ansible/bin/activate`
- Install Ansible `pip install ansible`

### Windows
- Install Linux.
- Goto setup for Linux.

## Execute Provisioning
### Install required roles from Ansible Galaxy
- Activate virtual environment `source ~/.venv/ansible/bin/activate`
- Install Postgresql Role `ansible-galaxy install anxs.postgresql`
- Install Minio Role `ansible-galaxy install atosatto.minio`

### Run Provisioning
- Execute `vagrant up` 
- Execute Ansible Playbook `ansible-playbook -i inventory.yaml playbook.yaml`

### Inspect Result
- Execute `vagrant ssh <vm-name>`

## Details
### Vagrant
Vagrant will install 4 VMs with following details   
| Name        | IP            | Hostname  |  Description |   
|:----------- |:------------- | ------------ |  ------ |    
| master | 192.168.33.10 | posgresql-master |  Postgresql Master |    
| minio | 192.168.33.11 | minio |  Minio Server to Test S3 |    
| slave-one | 192.168.33.12 | postgresql-slave-one | Postgresql Replication to master |    
| slave-two | 192.168.33.13 | postgresql-slave-one | Cascading Replication to slave-one |    

### Ansible role
Ansible will search role 

