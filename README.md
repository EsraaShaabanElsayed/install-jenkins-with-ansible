Sure! Here is a `README.md` file that fits the format you provided, with all necessary details about your Jenkins setup using Ansible:

```markdown
# Install Jenkins with Ansible

## Overview
This repository contains an Ansible playbook to install and configure Jenkins on a remote server. The playbook ensures that Java is installed, Jenkins directories have the correct permissions, and Jenkins runs on the default port (8080).

## Project Structure
```
install-Jenkins-with-ansible/
├── change_jenkins_port.yml
├── inventory
└── README.md
```

## Files
- `change_jenkins_port.yml`: Contains the main Ansible playbook that installs Java, sets up Jenkins, and ensures Jenkins runs on port 8080.
- `inventory`: Lists the remote servers where the playbook will be executed.
- `README.md`: Provides an overview and setup instructions.

## Setup Instructions

### Clone the Repository:
```sh
git clone https://github.com/your-username/install-jenkins-with-ansible.git
cd install-Jenkins-with-ansible
```

### Update the Inventory File:
Modify the `inventory` file to include your remote server's IP address or hostname.

### Run the Playbook:
```sh
ansible-playbook -i inventory change_jenkins_port.yml
```
Ensure you have permission to run the playbook with `sudo`.

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
    - Adjusts the ownership of Jenkins directories to the `Jenkins` user and group.
3. **Reinstall Jenkins**:
    - Ensures Jenkins is installed and up to date.
4. **Restart Jenkins Service**:
    - Restart the Jenkins service to apply the changes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Jenkins: [https://www.jenkins.io/](https://www.jenkins.io/)
- Ansible: [https://www.ansible.com/](https://www.ansible.com/)
```

