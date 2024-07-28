Here's the `README.md` content in a single markdown block:

```markdown
# Install Jenkins with Ansible

## Overview
This repository contains an Ansible playbook to install and configure Jenkins on a remote server. The playbook ensures that Java is installed, Jenkins directories have the correct permissions, and Jenkins runs on the default port (8080).


## Files
- `change_jenkins_port.yml`: Contains the main Ansible playbook that installs Java, sets up Jenkins, and ensures Jenkins runs on port 8080.
- `inventory`: Lists the remote servers where the playbook will be executed.
- `README.md`: Provides an overview and setup instructions.

## Setup Instructions

### Clone the Repository:
```sh
git clone https://github.com/your-username/install-jenkins-with-ansible.git
cd install-jenkins-with-ansible
```

### Update the Inventory File:
Modify the `inventory` file to include the IP address or hostname of your remote server.

### Run the Playbook:
```sh
ansible-playbook -i inventory change_jenkins_port.yml
```
Ensure you have the necessary permissions to run the playbook with `sudo`.

## Inventory Example

Create an `inventory` file to list your target servers:

```ini
[servers]
your_server_ip ansible_user=your_username ansible_ssh_private_key_file=~/.ssh/id_rsa
```
Replace `your_server_ip`, `your_username`, and the path to your SSH private key file as needed.

## Playbook Details

The playbook performs the following tasks:

1. **Install OpenJDK 11**:
    - Ensures OpenJDK 11 is installed on the server.
2. **Ensure Jenkins Directories Have Correct Permissions**:
    - Adjusts the ownership of Jenkins directories to the `jenkins` user and group.
3. **Reinstall Jenkins**:
    - Ensures Jenkins is installed and up to date.
4. **Restart Jenkins Service**:
    - Restarts the Jenkins service to apply the changes.

