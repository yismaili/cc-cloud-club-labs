# Beginner Project 03 - Vagrant Provisioning

## Subject

Rebuild the networking and web-server lab automatically with `vagrant up`.

## Learning Goals

- Describe virtual machines as code.
- Automate repeatable server configuration.
- Understand provisioning and idempotency.
- Test infrastructure from a clean environment.

## Mandatory Work

- Create a `Vagrantfile` for two supported Linux VMs.
- Configure hostnames, resources and private IP addresses.
- Configure SSH access and shared project files.
- Write separate provisioning scripts instead of placing all logic inline.
- Automatically install and configure NGINX, the two websites and TLS from Project 02.
- Automatically configure required firewall rules.
- Do not hard-code passwords, tokens or private keys.
- Make provisioning idempotent: running it twice must finish successfully.

## Deliverables

- `Vagrantfile`.
- Provisioning scripts.
- NGINX and website configuration.
- A README with `up`, `provision`, `halt` and `destroy` instructions.

## Validation

1. Run `vagrant destroy -f`.
2. Run `vagrant up`.
3. Verify both machines and both HTTPS websites.
4. Run `vagrant provision` again.
5. Confirm that nothing is duplicated or broken.

## Estimated Time

One to two weeks.
