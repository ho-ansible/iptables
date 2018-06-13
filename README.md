# Ansible role: iptables
Linux network firewall

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `iptables_policies`: list of hashes,
  each with a `chain` and a `policy`.
  Default policy for packets that don't match any rule
  in a chain. By default, policy is ACCEPT.
+ `iptables_ports`: numeric list of ports to open
  (both TCP and UDP).
+ `iptables_enable_ping`: whether to allow ICMP ping.
  Default true.

## Handlers
+ `iptables`: roles that set iptables rules may notify this handler to have the rules saved in case of reboot.

## Dependencies

## Example Playbook

```
- hosts: linux
  roles:
    - { role: ho-ansible.iptables }
```

## License
MIT

## Author Information
Sean Ho, https://github.com/ho-ansible/
