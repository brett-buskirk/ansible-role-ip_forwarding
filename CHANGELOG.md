# Changelog

All notable changes to ansible-role-ip_forwarding are documented here. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2025-02-18

### Added
- Support for NAT across multiple VPC network prefixes: the `iptables`
  POSTROUTING rule now iterates over a list, allowing more flexible network
  configurations.

### Changed
- **Breaking:** the `vpc_network_prefix` variable is replaced by
  `vpc_network_prefixes`, which expects a list of network prefixes. Existing
  playbooks must be updated to the new variable format.

[Unreleased]: https://github.com/brett-buskirk/ansible-role-ip_forwarding/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/brett-buskirk/ansible-role-ip_forwarding/releases/tag/v1.1.0
