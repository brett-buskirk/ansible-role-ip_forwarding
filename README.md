# ansible-role-ip_forwarding

This Ansible role enables IP forwarding and configures NAT using iptables.

## Requirements

* An Ubuntu-based system (tested on Ubuntu).
* Ansible installed.
* `vpc_network_prefix` variable defined with the VPC network address.

## Role Variables

* `vpc_network_prefix`: The network address of your VPC (e.g., "10.0.0.0/24").

## Dependencies

This role has no dependencies.

## Example Playbook

```yaml
- hosts: your_hosts
  become: true
  vars:
    vpc_network_prefix: "10.0.0.0/24" #replace with your vpc network.
  roles:
    - ansible-role-ip_forwarding
```

## Installation

You can install this role using Ansible Galaxy:

```shell
ansible-galaxy install brett-buskirk.net_tools
```

Or you can include it in your requirements.yml file:

```yaml
---
roles:
  - name: brett-buskirk.ip_forwarding
    src: https://github.com/brett-buskirk/ansible-role-ip_forwarding
    version: main # or a specific tag
```

Then install it using:

```shell
ansible-galaxy install -r requirements.yml
```

## Role Tasks

This role performs the following tasks:

- **Install `iptables-persistent`:** Installs the `iptables-persistent` package to save iptables rules across reboots.
- **Enable IP Forwarding:** Enables IP forwarding by setting `net.ipv4.ip_forward` to 1 in `sysctl`.
- **Persist IP Forwarding:** Uncomment the `net.ipv4.ip_forward` line in `/etc/sysctl.conf` to make the IP forwarding change permanent.
- **Configure NAT (Network Address Translation):** Configures iptables to perform NAT for traffic originating from the specified VPC network (`vpc_network_prefix`) to the public interface (`eth0`).
- **Persist NAT Configuration:** Saves the iptables rules to `/etc/iptables/rules.v4` to ensure the NAT configuration persists across reboots.

## Usage

Include the role in your playbook as shown in the "Example Playbook" section. The role will automatically install the necessary packages on the target host.

## License

MIT

## Author Information

This role was created by Brett Buskirk for RC Journey.

## Galaxy Tags

```
networking, iptables, nat, ip_forwarding
```
