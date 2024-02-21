# Deploy Node Aleo

This repository contains Ansible scripts for installing, updating, and removing an Aleo node on Linux systems. The playbook simplifies the process of setting up an Aleo node, managing its services, and viewing logs for debugging and monitoring.

## Prerequisites
A Linux system Ubuntu 22.04 TLS with root.
Git and Ansible installed on your machine.
Getting Started

## Step 1: Installing Dependencies
Update your system's package list:
```
sudo apt update && sudo apt upgrade -y
```

Install Ansible and Git:
```
sudo apt install ansible git -y
```

## Step 2: Downloading the Project
Clone this repository to get the Ansible playbook and all necessary files:
```
git clone https://github.com/nodemasterpro/deploy-node-aleo.git
cd deploy-node-aleo
```

## Step 3: Executing the Playbook
Run the playbook using the following command. You'll be prompted to specify the action (install, update, or remove):
```
ansible-playbook aleo_node.yml
```
Ensure you're running the playbook with root privileges or via a user with sudo access.

##  Step 4: Managing the Aleo Node
Starting Services:
To start the Aleo client or prover service:

```
sudo systemctl start aleo-client
```
then
```
sudo systemctl start aleo-prover
```
Stopping Services:
To stop the services:
```
sudo systemctl stop aleo-client
```
then
```
sudo systemctl stop aleo-prover
```
## Step 5: Viewing Logs
To view the logs for the Aleo client or prover:

Logs aleo client: 
```
journalctl -u aleo-client -f -o cat
```
Logs aleo prover: 
```
journalctl -u aleo-prover -f -o cat
```
## Additional Note
After installation or update, the Aleo account keys are stored in /root/aleo/account_new.txt. Please ensure to check this location for your keys. 