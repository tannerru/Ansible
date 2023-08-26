# Configure System Ansible Playbook

This Ansible playbook is designed to automate the configuration of various system settings on remote hosts using Ansible Semaphore. The playbook performs tasks such as setting DNS, enabling password authentication, joining an Active Directory domain, disabling FQDN in SSSD configuration, and rebooting the server.

## Prerequisites

- Ansible Semaphore installed and configured.
- Proper SSH connectivity and credentials to target hosts.
- Roles used in the playbook (`dns` and `thulium_drake.adjoin`) should be available and correctly configured in Semaphore.

## Usage with Ansible Semaphore

1. Install and configure Ansible Semaphore by following the [official documentation](https://ansible-semaphore.github.io/installation/).

2. Create a new project in Ansible Semaphore and link it to your GitHub repository where the playbook is stored.

3. In Semaphore, create a new playbook using the Semaphore's UI and copy the contents of `linux_adjoin.yml` into the playbook's content.

4. Configure the inventory file within the Semaphore UI. You can define your target hosts' details, such as IP addresses or hostnames.

5. Set up the playbook variables within Semaphore. Configure the variables under each task in the Semaphore UI, replacing the placeholders with your environment-specific values.

6. Create a new task in Semaphore and link it to your playbook.

7. Launch the task in Semaphore. The playbook will connect to each target host, perform the specified tasks, and configure the system settings accordingly.

## Playbook Structure

The playbook is structured as follows:

- `Set DNS`: Sets DNS servers, DNSSEC, and domains using the `dns` role.
- `Enable Password Authentication`: Enables password authentication for SSH.
- `Join to AD`: Joins the host to an Active Directory domain using the `thulium_drake.adjoin` role.
- `Disable FQDN in SSSD configuration`: Adjusts SSSD configuration.
- `Reboot the server`: Reboots the server with a delay.
- `Wait for the reboot and reconnect`: Waits for the server to be reachable again.

## Active Directory Configuration

Before running the playbook, update the `adjoin_domains` section in the Enviroment.json with your specific Active Directory settings.

## Notes

- Make sure to review and customize the variables and configurations in the playbook to match your environment's requirements.
- Always test the playbook on a non-production environment before applying to production systems.

## License

This project is licensed under the [MIT License](LICENSE).
