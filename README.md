# Jenkins Ansible Playbook

This repository contains an Ansible playbook designed to install and configure Jenkins on target servers. The playbook automates the setup process, ensuring that Jenkins is installed with the necessary dependencies and configured for immediate use.

## Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements)
- [Inventory](#inventory)
- [Playbook Structure](#playbook-structure)
- [Roles](#roles)
  - [InstallJava](#installjava)
  - [AddJenkinsRepo-Key](#addjenkinsrepo-key)
  - [InstallJenkins](#installjenkins)
  - [EnableJenkins](#enablejenkins)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This playbook is used to automate the installation and configuration of Jenkins on target servers. It ensures that all necessary dependencies are installed and Jenkins is properly set up and enabled to run.

## Requirements

- Ansible 2.9+
- Target servers running a supported Linux distribution (e.g., Ubuntu, CentOS)
- SSH access to the target servers with a user that has sudo privileges

## Inventory

Define your target servers in the `inventory` file. Example:

```
[servers]
server1 ansible_host=192.168.1.10 ansible_user=your_user
server2 ansible_host=192.168.1.11 ansible_user=your_user
```

## Playbook Structure

- `installJenkins.yml`: The main playbook file that orchestrates the Jenkins installation and configuration.
- `roles/`: Directory containing all the roles used by the playbook.
  - `InstallJava/`
    - `tasks/`: Contains the task files for installing Java.
      - `main.yml`: Main task file for the role.
  - `AddJenkinsRepo-Key/`
    - `tasks/`: Contains the task files for adding the Jenkins repository and GPG key.
      - `main.yml`: Main task file for the role.
  - `InstallJenkins/`
    - `tasks/`: Contains the task files for installing Jenkins.
      - `main.yml`: Main task file for the role.
  - `EnableJenkins/`
    - `tasks/`: Contains the task files for enabling and starting the Jenkins service.
      - `main.yml`: Main task file for the role.
- `inventory`: Inventory file specifying the target servers.

## Roles

### InstallJava

This role installs the Java runtime environment required by Jenkins.

### AddJenkinsRepo-Key

This role adds the Jenkins repository and its GPG key to the target servers.

### InstallJenkins

This role installs Jenkins from the official Jenkins repository.

### EnableJenkins

This role enables and starts the Jenkins service, ensuring it is running and enabled on boot.

## Usage

1. Clone this repository:
    ```bash
    git clone <repository_url>
    cd jenkinsPlaybook
    ```

2. Update the `inventory` file with your target server details.

3. Run the playbook:
    ```bash
    ansible-playbook -i inventory installJenkins.yml
    ```

