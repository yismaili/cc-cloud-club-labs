# Beginner Project 09 - Secure VMs with Terraform and Vagrant

## Subject

Create and secure a local multi-VM infrastructure with Terraform, Vagrant and VirtualBox. Terraform is the main interface. The Terraform Vagrant provider runs the `Vagrantfile`, and Vagrant creates and manages the virtual machines.

The finished VMs must behave like small VPS servers and have Docker Engine and Docker Compose v2 installed automatically.

## Architecture

```text
terraform apply
       |
       v
Terraform Vagrant provider
       |
       v
Vagrantfile and Vagrant CLI
       |
       v
VirtualBox
├── web-1
├── web-2
└── database
```

## Learning Goals

- Use Terraform variables, resources, outputs and state.
- Use Terraform to control a Vagrant multi-machine environment.
- Define VM resources, networks and storage in a `Vagrantfile`.
- Apply basic VPS security to Linux machines.
- Install Docker Engine and Docker Compose automatically.
- Write repeatable and idempotent provisioning scripts.
- Verify that private services are not exposed to the host.

## Important Tool Limitation

This project uses the community `bmatcuk/vagrant` Terraform provider. It runs the local Vagrant CLI and reads the selected `Vagrantfile`. It is suitable for this learning lab, but it is not an official HashiCorp provider and must not be presented as a production architecture.

Removing only one machine from a multi-machine `Vagrantfile` may leave an orphan VM. Students must destroy that machine before removing its definition, or destroy and rebuild the complete lab.

## Prerequisites

- Terraform.
- Vagrant.
- VirtualBox or another instructor-approved Vagrant provider.
- Hardware virtualization enabled.
- At least 4 CPU threads, 8 GB RAM and 30 GB free disk space recommended.
- A host-only subnet that does not conflict with an existing local network.

## Required VM Topology

Create three Linux VMs using a supported Debian or Ubuntu Server release:

| VM | Purpose | Frontend IP | Backend IP |
| --- | --- | --- | --- |
| `web-1` | First Docker application host | `192.168.56.21` | `192.168.57.21` |
| `web-2` | Second Docker application host | `192.168.56.22` | `192.168.57.22` |
| `database` | Private Docker database host | None | `192.168.57.30` |

The addresses may be changed to avoid conflicts, but the design must keep the frontend and backend networks separate.

## Terraform Requirements

- Pin the Terraform version and `bmatcuk/vagrant` provider version.
- Use a `vagrant_vm` resource that points to the directory containing the `Vagrantfile`.
- Use variables for VM names, CPU, memory, IP addresses and the selected box version.
- Pass approved values to the Vagrant environment instead of generating untracked configuration.
- Create outputs for VM names, private IP addresses and safe SSH commands.
- Commit `.terraform.lock.hcl`.
- Ignore state, saved plans, local variable files, generated keys and VirtualBox metadata.
- Do not put passwords or private keys in Terraform code or state intentionally.
- Use Terraform as the normal lifecycle interface; direct Vagrant commands are only for troubleshooting and orphan cleanup.

## Vagrant Requirements

- Define all three machines in one `Vagrantfile`.
- Pin a supported box version.
- Configure hostnames, CPU, memory and private network interfaces.
- Keep the database VM off the frontend network.
- Use Vagrant's generated SSH key behavior or a project-specific generated key. Do not commit private keys.
- Keep provisioning logic in separate scripts.
- Make every provisioning script safe to run more than once.
- Add a persistent virtual disk for database data when supported by the selected Vagrant provider.

## VPS Security Requirements

Apply the following rules to every VM:

- Create a non-root administrative user.
- Use SSH key authentication.
- Disable root SSH login.
- Disable SSH password authentication after key access has been tested.
- Use a default-deny incoming firewall policy.
- Allow SSH only from the host or approved management subnet.
- Install security updates during provisioning.
- Enable automatic security updates.
- Install and enable Fail2ban for SSH.
- Enable time synchronization.
- Remove or disable services that are not required.
- Configure a clear hostname and correct `/etc/hosts` entries.
- Do not expose the Docker daemon socket or API over the network.
- Do not store real secrets in provisioning scripts, Terraform files or the `Vagrantfile`.

Do not break Vagrant's SSH access while hardening the machines. Verify key-based access before disabling password authentication and keep the key used by Vagrant available to the Terraform Vagrant provider.

## Firewall Rules

- `web-1` and `web-2` may accept ports `80` and `443` on the frontend network.
- SSH must be limited to the host or management subnet.
- The database service port must be allowed only from `web-1` and `web-2` on the backend network.
- The database service port must not be reachable directly from the host or frontend network.
- All other incoming traffic must be denied unless it is documented and approved.

## Docker Requirements

Install the following on all three VMs:

- Docker Engine from an approved package source.
- Docker Compose v2 as the Docker CLI plugin.
- Required container runtime dependencies.

Configuration requirements:

- Enable and start Docker at boot.
- Verify Docker with a small test container.
- Verify Compose with `docker compose version`.
- Configure Docker log rotation so container logs cannot fill the disk.
- Do not publish database ports on the frontend interface.
- Use restart policies for long-running containers.
- Add only the approved deployment user to the `docker` group, and document that Docker group membership provides root-equivalent control of the host.

The project focuses on infrastructure creation and host preparation. A small NGINX container and a small database container may be used to prove connectivity; a complete application is not required.

## Required Workflow

```bash
terraform init
terraform fmt -check
terraform validate
terraform plan -out=tfplan
terraform apply tfplan
terraform output
terraform plan
terraform destroy
```

After the first successful apply, a second `terraform plan` should not propose unintended infrastructure changes.

## Security Validation

Students must demonstrate:

```bash
sshd -T
sudo ufw status verbose
sudo ss -tulpn
sudo fail2ban-client status sshd
systemctl is-enabled unattended-upgrades
systemctl is-active docker
docker version
docker compose version
```

They must also test:

- Root SSH login fails.
- Password-based SSH login fails.
- Key-based SSH login succeeds.
- HTTP or HTTPS reaches the web VMs.
- The web VMs can reach the database service over the backend network.
- The host cannot reach the database service port.
- Docker and the test containers return after a VM reboot.

## Deliverables

- Terraform configuration with pinned provider versions, variables and outputs.
- One multi-machine `Vagrantfile`.
- Separate, idempotent provisioning and hardening scripts.
- `.terraform.lock.hcl` and a safe `.gitignore`.
- `terraform.tfvars.example` containing no secrets.
- A network and traffic-flow diagram.
- A README with prerequisites, deployment, verification, troubleshooting and cleanup instructions.
- A short security report listing open ports, enabled services and accepted risks.

## Evaluation Rules

The project fails if:

- A password, token or private key is committed.
- Root or password-based SSH login remains enabled without an approved reason.
- The database port is reachable from the host or frontend network.
- Docker is installed manually after `terraform apply`.
- Provisioning fails on a second run.
- `terraform destroy` leaves undocumented running VMs.

## Cleanup

Run `terraform destroy` and verify that all lab VMs are removed. If a VM was removed from the `Vagrantfile` before it was destroyed, clean it up explicitly and run:

```bash
vagrant global-status --prune
```

Document any resource that requires manual cleanup.

## Estimated Time

Two to three weeks.

<p align="center">
  <img src="../images/terraform.png" alt="Terraform combines infrastructure tools" width="600">
</p>
