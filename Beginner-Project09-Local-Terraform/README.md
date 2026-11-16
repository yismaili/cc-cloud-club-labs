# Beginner Project 09 - Local VMs with Terraform and Vagrant

## Subject

Build the same local virtual-machine infrastructure in two ways: first with Vagrant, then with Terraform and the libvirt provider.

This project does not make Terraform execute Vagrant. Each tool creates its own version of the same lab so students can compare their workflows safely.

## Architecture

```text
Student Linux machine or instructor lab host
├── Vagrant implementation
│   ├── web-1 VM
│   ├── web-2 VM
│   └── database VM
└── Terraform implementation
    ├── libvirt network
    ├── web-1 VM
    ├── web-2 VM
    ├── database VM
    └── persistent database disk
```

Run only one implementation at a time unless the machine has enough resources and the networks do not overlap.

## Learning Goals

- Understand how Vagrant and Terraform manage VM lifecycles.
- Create local VMs, virtual networks and storage as code.
- Understand Terraform providers, resources, variables, outputs and state.
- Use cloud-init to bootstrap a VM.
- Use `terraform plan` before making infrastructure changes.
- Detect infrastructure drift.
- Compare a development-environment tool with an Infrastructure as Code tool.

## Prerequisites

- A Linux host with hardware virtualization enabled.
- KVM and libvirt for the Terraform implementation.
- Vagrant with a compatible provider for the Vagrant implementation.
- Enough capacity for three small VMs. A practical minimum is 4 CPU threads, 8 GB RAM and 30 GB free disk space.

Students who cannot run KVM locally should use an instructor-provided Linux lab host.

## VM Topology

Create three VMs:

| VM | Purpose | Example private IP |
| --- | --- | --- |
| `web-1` | First web server | `192.168.56.21` |
| `web-2` | Second web server | `192.168.56.22` |
| `database` | Private database server | `192.168.57.30` |

The exact addresses may be changed to avoid conflicts. The final design must include:

- A public or frontend network for the web VMs.
- A private backend network shared by the web VMs and database VM.
- No database port exposed to the host network.
- SSH access using keys.
- A persistent disk attached to the database VM.

## Part 1 - Vagrant Implementation

- Reuse and extend the ideas from Project 03.
- Create the three VMs in one `Vagrantfile`.
- Pin the Vagrant box version.
- Define hostnames, CPU, memory and network interfaces.
- Add a persistent disk for the database VM if the selected provider supports it.
- Use provisioning only for basic bootstrap tasks such as users, SSH keys and required packages.
- Start the complete lab with `vagrant up`.
- Verify it, stop it with `vagrant halt`, and remove it with `vagrant destroy`.

## Part 2 - Terraform Implementation

- Recreate the same VM topology using Terraform.
- Use the `dmacvicar/libvirt` provider with a pinned version.
- Create libvirt networks, storage volumes and virtual-machine domains as Terraform resources.
- Use a supported Linux cloud image and cloud-init.
- Create at least one reusable VM module.
- Use typed variables for VM names, CPU, memory, disk size and network addresses.
- Produce outputs for VM names, IP addresses and safe SSH connection information.
- Commit `.terraform.lock.hcl`.
- Ignore Terraform state, saved plans, local variable files, generated disks and secrets.
- Never use `local-exec` to run `vagrant up` from Terraform.

## Required Terraform Workflow

```bash
terraform init
terraform fmt -check
terraform validate
terraform plan -out=tfplan
terraform apply tfplan
terraform output
terraform destroy
```

## Change and Drift Exercises

- Change one web VM's memory or CPU using Terraform and review the plan before applying it.
- Add a third web VM using a variable such as `web_instance_count`.
- Change one Terraform-managed resource manually with `virsh`.
- Run `terraform plan` and explain the detected drift.
- Restore the declared configuration through Terraform.

Do not create drift by editing the Terraform state file.

## Comparison Report

Create `VAGRANT_VS_TERRAFORM.md` and answer:

- Which files describe the VMs in each implementation?
- How does each tool track infrastructure?
- What happens when a VM is changed manually?
- How does each tool create, update and destroy machines?
- Which tool is easier for a developer workstation?
- Which approach is closer to managing cloud infrastructure?
- Why should Terraform not call Vagrant through `local-exec`?

## Deliverables

- `vagrant/Vagrantfile` and its bootstrap scripts.
- `terraform/` containing providers, modules, variables, outputs and environment values.
- Cloud-init configuration for the Terraform VMs.
- `.terraform.lock.hcl`, `.gitignore` and `terraform.tfvars.example`.
- `VAGRANT_VS_TERRAFORM.md`.
- A README with prerequisites, commands, tests, cleanup and troubleshooting.

## Important State and Security Rules

- Never commit Terraform state or saved plan files.
- Terraform state may contain sensitive values even when variables are marked sensitive.
- Never place passwords or private SSH keys in the Vagrantfile, Terraform code or cloud-init files committed to Git.
- Use generated keys or instructor-approved secret handling.
- Document how remote encrypted state and locking would work for a real team.

## Validation

- `vagrant up` creates the complete three-VM Vagrant lab.
- `vagrant destroy` removes the Vagrant-managed VMs.
- `terraform apply` creates the equivalent three-VM libvirt lab.
- The web VMs can reach the private database service.
- The host cannot directly reach the database service port.
- Terraform detects the demonstrated manual drift.
- `terraform destroy` removes the Terraform-managed VMs, networks and disks selected for destruction.
- A clean rebuild succeeds for both implementations.

## Estimated Time

Two to three weeks.

<p align="center">
  <img src="../images/terraform.png" alt="Terraform combines infrastructure tools" width="600">
</p>
