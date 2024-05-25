# Deploy Node Berachain
This repository contains Ansible scripts for installing, updating, and removing a Berachain node on Linux systems. The playbook simplifies the process of setting up a Berachain node, managing its services, and ensuring that key transactions are recognized before proceeding with node operations.

## Prerequisites
A Linux system (Ubuntu 22.04 LTS recommended) with root access.
Git and Ansible installed on your machine.

## Getting Started
### Step 1: Installing Dependencies
Update your system's package list:

```
sudo apt update && sudo apt upgrade -y
```
Install Ansible and Git:
```
sudo apt install ansible git -y
```

### Step 2: Downloading the Project
Clone this repository to get the Ansible playbook and all necessary files:
```
git clone https://github.com/nodemasterpro/deploy-node-berachain.git
cd deploy-node-berachain
```

### Step 3: Executing the Playbook
Run the playbook using the following command:
```
ansible-playbook bera_node.yml -e node_action="install"
```
Ensure you're running the playbook with root privileges or via a user with sudo access. The bearchain node is started after installation.


### Step 4: Viewing Logs
To view the logs for the Berachain node:
```
journalctl -u berachain-node -f -o cat
```

## Additional Note

After installation , the Berachain node's adress and your mnemonic phrase are stored in the specified log file located at /root/berachain/output.log. Please ensure to check this location for your  mnemonic phrase and node adress.

Stopping Services:
To stop the service:
```
sudo systemctl stop berachain-node
```

Starting Services:
To start the Berachain node service:
```
sudo systemctl start berachain-node
```

Remove berachain node: 
To remove the berachain node, run the playbook using the following command:
```
ansible-playbook berachain_node.yml -e node_action="remove"
```
 For any questions, reach out on my Discord. Follow updates on Twitter, join the Telegram Group, the Discord Server, and subscribe to the YouTube Channel.
