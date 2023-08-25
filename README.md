# Ansible Playbooks Repository

Welcome to my collection of Ansible playbooks! This repository contains a set of automation scripts that I use to provision, configure, and manage various services and systems.

## About

These Ansible playbooks are designed to make the deployment and management of infrastructure and applications more efficient and consistent. Whether you're setting up servers, configuring services, or maintaining a homelab, these playbooks provide reusable and easily customizable automation solutions.

## Contents

Here's a brief overview of the playbooks and roles included in this repository:

- `Linux/AD-Join`: Configures DNS, Enables SSH Password Authentication, Joins AD, Disables FQDN, Reboot & Wait
- `Linux/apt_update.yml`: Simple playbook to run "apt update"
- `Linux/apt_distro_upgrade.yml`: Simple playbook to run apt dist-upgrade

### Roles

In addition to the playbooks, this repository also includes the following roles:

- `thulium_drake.adjoin`: Common configurations for all servers.
- `ansible-role-dns`: Role for setting up a web server.

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/tannerru/Ansible.git
