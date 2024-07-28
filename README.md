# Jenkins Setup with Ansible

This repository contains an Ansible playbook to install and configure Jenkins on a remote server. The playbook ensures that Java is installed, Jenkins directories have the correct permissions, and Jenkins runs on a non-conflicting port (8081).

## Requirements

- Ansible 2.9 or higher
- A remote server with Ubuntu
- SSH access to the remote server

## Files

- `change_jenkins_port.yml`: The main Ansible playbook that installs Java, sets up Jenkins, and changes the Jenkins port to avoid conflicts.

## Usage

1. **Clone the repository**:

    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Update the inventory file**:

    Modify the `inventory` file to include the IP address or hostname of your remote server.

3. **Run the playbook**:

    ```sh
    ansible-playbook -i inventory change_jenkins_port.yml
    ```

    Ensure you have the necessary permissions to run the playbook with `sudo`.

## Inventory Example

Create an `inventory` file to list your target servers:

```ini
[servers]
your_server_ip ansible_user=your_username ansible_ssh_private_key_file=~/.ssh/id_rsa
