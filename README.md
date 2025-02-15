# ansible-role-ip_forwarding

This Ansible role enables IP forwarding and configures NAT using iptables.

## Requirements

* An Ubuntu-based system (tested on Ubuntu).
* Ansible installed.
* `vpc_network_prefix` variable defined with the VPC network address.

## Role Variables

* `vpc_network_prefix`: The network address of your VPC (e.g., "10.0.0.0/24").

## Example Playbook

```yaml
- hosts: your_hosts
  become: true
  vars:
    vpc_network_prefix: "10.0.0.0/24" #replace with your vpc network.
  roles:
    - ansible-role-ip_forwarding
```
