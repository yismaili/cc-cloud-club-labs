# Beginner Project 01 - Networking Fundamentals

## Subject

Connect two Linux virtual machines and learn how traffic moves between hosts and services.

## Learning Goals

- Understand IP addresses, subnet masks, gateways, ports and protocols.
- Understand the basic roles of DNS, TCP, UDP, HTTP and SSH.
- Inspect routes, listening ports and network connections.
- Control traffic with a host firewall.

## Mandatory Work

- Create two Linux VMs on the same private network.
- Give them fixed private IP addresses from an instructor-approved subnet.
- Add simple local names such as `server1.cloudclub.test` and `server2.cloudclub.test`.
- Test connectivity using `ping`, `ip`, `ss`, `curl`, `dig` or equivalent tools.
- Configure SSH key access from one VM to the other.
- Run a simple HTTP service on one VM and access it from the other.
- Configure firewall rules that allow SSH and HTTP, then demonstrate one blocked port.
- Capture and explain one DNS request and one HTTP request using `tcpdump` or Wireshark.

## Deliverables

- A small network diagram.
- IP and hostname configuration.
- Firewall rules.
- A README containing the test commands and expected results.

## Validation

- Both machines can reach each other by IP and local name.
- The allowed service is reachable.
- The blocked service is not reachable.
- The student can explain the path of one request.

## Estimated Time

One week.
