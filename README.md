# Ansible Playbook for PostgreSQL Setup

This Ansible playbook automates the setup and configuration of PostgreSQL on RHEL, CentOS, Fedora, and Ubuntu servers. It ensures that your system is updated, configures the necessary PostgreSQL repository, installs PostgreSQL, initializes the database cluster, starts and enables the PostgreSQL service, and verifies the installation by checking the PostgreSQL version.

## Prerequisites

- **Ansible 2.9** or later.
- A managed node (target server) running **RHEL**, **CentOS**, **Fedora**, or **Ubuntu**.
- **SSH access** to the managed node with **sudo privileges**.

## Playbook Tasks Overview

For **RHEL**, **CentOS**, and **Fedora**:
1. **Pull Latest Updates**: Updates all packages to their latest versions using DNF or YUM.
2. **Set the PostgreSQL Yum Repository**: Configures the official PostgreSQL repository for the respective distribution.

For **Ubuntu**:
1. **Pull Latest Updates**: Updates all packages to their latest versions using APT.
2. **Add the PostgreSQL Repository**: Adds the official PostgreSQL apt repository.
3. **Import the PostgreSQL GPG Key**: Ensures the authenticity of the PostgreSQL repository by importing its GPG key.

Common tasks for all distributions:
1. **Install PostgreSQL**: Installs the PostgreSQL server along with contrib packages.
2. **Start and Enable PostgreSQL**: Ensures the PostgreSQL service is running and enabled to start on boot.
3. **Check PostgreSQL Version**: Verifies the installation by checking the PostgreSQL version.
4. **Error Handling**: Optionally fails the playbook execution with a custom message if PostgreSQL was not installed correctly.

## How to Use

1. Ensure Ansible is installed and configured on your control node.
2. Customize the inventory file (`hosts` file) to include the servers where you want to install PostgreSQL.
3. Adapt the playbook to match your specific requirements, such as adjusting the PostgreSQL version if necessary.
4. Run the playbook using the following command:

```bash
ansible-playbook -i your_inventory_file playbook_name.yml
