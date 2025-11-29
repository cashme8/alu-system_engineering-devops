# Firewall

## Overview

This project focuses on implementing and configuring firewalls on servers, specifically using the `ufw` (Uncomplicated Firewall) tool. The tasks involve setting up rules to filter incoming traffic and performing port forwarding.

**Author:** Sylvain Kalache, co-founder at Holberton School

**Weight:** 1

**Project Start:** Feb 12, 2024 6:00 AM

**Project End:** Feb 13, 2024 6:00 AM

**Checker Release:** Feb 12, 2024 12:00 PM

**Auto Review:** An auto review will be launched at the deadline.

## Concepts

This project is designed to reinforce the understanding of the following concept:

- Web stack debugging

## Background Context

Firewalls play a crucial role in securing servers. The absence of a firewall can lead to potential security vulnerabilities. The provided information emphasizes the importance of firewalls and the specific requirements for the tasks in this project.

## Resources

To successfully complete this project, it is recommended to read or watch:

- What is a firewall

## More Info

The project encourages students to use `telnet` as a tool to check if sockets are open. The provided example demonstrates how to use `telnet` to check if a port is open on a server. Additionally, the project mentions the school network filtering outgoing connections, requiring testing from outside the school network.

**Warning:** Containers on demand cannot be used for this project due to Docker container limitations.

## Quiz Questions

There is a set of quiz questions provided, covering topics related to firewalls and server configurations.

## Tasks

### Task 0: Block all incoming traffic but

- Install the `ufw` firewall on `web-01`.
- Configure `ufw` to block all incoming traffic except for specific TCP ports (22, 443, 80).
- Share the `ufw` commands used in the answer file.

**Repo:**
- GitHub repository: `alu-system_engineering-devops`
- Directory: `firewall`
- File: `0-block_all_incoming_traffic_but`

### Task 1: Port forwarding (Advanced)

- Configure `web-01` to redirect traffic from port 8080/TCP to port 80/TCP.
- Provide the modified `ufw` configuration file as the answer.

**Terminal in web-01:**
```bash
root@03-web-01:~# netstat -lpn
# (Output of netstat command)
```

**Terminal in web-02:**
```bash
ubuntu@03-web-02:~$ curl -sI web-01.holberton.online:80
# (Output of curl command for port 80)
ubuntu@03-web-02:~$ curl -sI web-01.holberton.online:8080
# (Output of curl command for port 8080)
```

**Repo:**
- GitHub repository: `alu-system_engineering-devops`
- Directory: `firewall`
- File: `100-port_forwarding`

## Warning

Be cautious when configuring firewall rules, as incorrect configurations, especially blocking port 22/TCP, can result in loss of SSH access to the server. Additionally, the use of `ufw` implies that port 22 is blocked by default, so it should be unblocked before logging out of the server.
