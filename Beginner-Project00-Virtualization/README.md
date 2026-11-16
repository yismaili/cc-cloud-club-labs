# Beginner Project 00 - Virtualization

## Subject

Build your first Linux server inside a virtual machine and secure it like a small real server.

## Learning Goals

- Understand hosts, guests, hypervisors and virtual hardware.
- Install and operate a Linux server.
- Manage users, permissions, services and logs.
- Configure secure remote access and a firewall.
- Automate a small task with Bash and cron.

## Mandatory Work

- Create one VM using VirtualBox or another instructor-approved hypervisor.
- Install a supported Debian or Ubuntu Server release.
- Set the hostname to `<login>-CC`.
- Create a lowercase non-root user and give it controlled sudo access.
- Configure SSH key authentication on port `1111` and disable root SSH login.
- Configure a firewall that allows SSH. Open other ports only when a documented service needs them.
- Create `monitoring.sh` to report architecture, CPU, memory, disk, boot time, users, network and active connections.
- Run the monitoring script every 10 minutes with cron and save its output to a log.
- Install one simple service and explain how to start, stop, restart and test it.

## Deliverables

- VM configuration notes.
- `monitoring.sh`.
- Firewall and SSH verification commands.
- A README with setup, testing and troubleshooting notes.

## Validation

- Root cannot log in through SSH.
- The student can connect using an SSH key on port `1111`.
- Only documented ports are open.
- The monitoring job runs without errors.
- The deployed service survives a reboot.

## Estimated Time

One to two weeks.

<p align="center">
  <img src="../images/next-level.png" alt="Hit the next level" width="600">
</p>
