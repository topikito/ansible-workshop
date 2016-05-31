# Task 1

## Problem

- Setup a Vagrant environment in this folder using the provided `Vagrantfile`
  - `vagrant up`
- Use the `ansible` command with the `ping` module to ensure its alive. Whats happening?
  - `ansible all -i inventory/local -m ping`
- Use `ansible` to check which user is performing the actions on the machine.
  - `ansible all -i inventory/local -m command -a "whoami"`