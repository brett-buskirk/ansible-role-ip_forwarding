# Roadmap

This is a small, stable Ansible role that enables IPv4 forwarding and configures
NAT via iptables on Ubuntu hosts. It is feature-complete for its purpose and in
**maintenance mode** — changes are limited to fixes, compatibility updates, and
small quality improvements.

## Maintenance
- [ ] Keep pace with supported Ubuntu LTS releases and Ansible versions.
- [ ] Align the README with the current `vpc_network_prefixes` (list) variable;
      the examples still reference the removed `vpc_network_prefix` scalar.

## Nice-to-have
- [ ] Make the public NAT interface configurable instead of hardcoding `eth0`.
- [ ] Add IPv6 forwarding (`net.ipv6.conf.all.forwarding`) as an opt-in variable.
- [ ] Add a Molecule scenario to smoke-test the role in CI.
