# Ansible Playbook for PostgreSQL Setup

This Ansible playbook automates the setup and configuration of PostgreSQL on RHEL, CentOS, and Fedora servers. It ensures that your system is updated, configures the necessary PostgreSQL yum repository, installs PostgreSQL 14 server, initializes the database cluster, starts and enables the PostgreSQL service, and verifies the installation by checking the PostgreSQL version.

## Prerequisites

- **Ansible 2.9** or later.
- A managed node (target server) running **RHEL**, **CentOS**, or **Fedora**.
- **SSH access** to the managed node with **sudo privileges**.

## Playbook Tasks Overview

1. **Pull Latest Updates**: Updates all packages to their latest versions using DNF (applicable for Fedora) or YUM.
2. **Set the PostgreSQL Yum Repository**: Adds the official PostgreSQL repository for CentOS/RHEL or Fedora, depending on the distribution.
3. **Install PostgreSQL 14 Server**: Installs the PostgreSQL 14 server package.
4. **Create DB Cluster Instance**: Initializes the PostgreSQL database cluster.
5. **Start and Enable PostgreSQL**: Ensures that the PostgreSQL service is running and enabled to start on boot.
6. **Check PostgreSQL Version**: Verifies the PostgreSQL installation by checking its version.
7. **Fail on PostgreSQL Error**: Fails the playbook execution with a custom message if PostgreSQL was not installed correctly.

## How to Use

1. Ensure you have Ansible installed and configured on your control node.
2. Customize the inventory file to include the servers where you want to install PostgreSQL.
3. Run the playbook using the following command:

   ```bash
   ansible-playbook -i your_inventory_file playbook_name.yml
