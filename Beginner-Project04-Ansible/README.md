# Beginner Project 04 - Configuration Management with Ansible

## Subject

Configure several Linux machines from one controller using reusable Ansible automation.

## Learning Goals

- Understand inventories, modules, playbooks and roles.
- Manage remote machines over SSH.
- Use variables, templates, handlers and secrets safely.
- Write idempotent configuration automation.

## Mandatory Work

- Reuse or adapt the Vagrant lab from Project 03.
- Create one controller and at least two managed nodes.
- Create an inventory with groups and host variables.
- Write roles for a common base configuration and a web-server configuration.
- Create users, install packages and deploy configuration files.
- Deploy the two HTTPS websites from Project 02.
- Use handlers to restart services only when configuration changes.
- Store sensitive values with Ansible Vault if the project needs them.
- Add tags for at least two parts of the playbook.

## Deliverables

- Vagrant lab definition.
- Ansible inventory, playbooks, roles and templates.
- `requirements.yml` if external collections are used.
- A README explaining how to run and test the automation.

## Validation

- `ansible all -m ping` succeeds.
- The first playbook run configures the nodes.
- The second run reports no unnecessary changes.
- Both HTTPS websites work after a reboot.

## Estimated Time

One to two weeks.
