# Task 1

Ansible is an independent provisioning tool that works with no agent on the client host. This means theres no need to
use a specific version of any OS to be able to start working. Other provisioning tools like Puppet require an interpreter
in the client so they can communicate and interact with the machine. Ansible avoids this by using Python and SSH.

Remember when I said you don't need any agent in the client? I kind of lied: you just need Python. I've found myself in
a situation where I wanted to provision an Ubuntu AMI in AWS and it did not have Python installed by default. I had to
use the AMI, manually connect and install Python, then create a custom AMI and then be able to automatically provison
my instance.

Now that we have a bit of context, lets get started! For using Ansible locally, we will be using
[Vagrant](https://www.vagrantup.com/downloads.html) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads).

## Tools we will be using
Assuming we have Vagrant and VirtualBox installed in our locals, we will just need Ansible to start working. Check the [Ansible installation page](http://docs.ansible.com/ansible/intro_installation.html#installation) for more information on how to do this on your preferred OS.

Once having Ansible installed (check with `ansible --version`) lets explain what we can do with it.

### `ansible`

This command allows you to interact individually with Ansible. This means you will be able to perform a single action which may affect 1 or many hosts.

### `ansible-playbook`

The most powerful option is to group single `ansible` operations to perform a series of actions that will end in a general purpose script. This can be done with playbooks. Imagine you wan't to install `nginx` and configure the hosts for it. One action is ensuring `nginx` is installed, and another action can be to set the configurations.

With playbooks, you define *roles* for grouping general purpose actions. In the example before, a role could be "nginx" as you'd like to install and configure it. This will be explained in Task 2.

### `ansible-galaxy`
The Ansible galaxy is a community driven repository where you can find contributions from other users. These contributions are *roles* that you can just get and run out of the box (Some config variables may have be changed).



#### Others
Ther are other ansible commands installed, but as for this workshop, we will not be using them.


## Problem

- Setup a Vagrant environment in this folder using the provided `Vagrantfile`
- Use the `ansible` command with the `ping` module to ensure its alive. Whats happening?
- Use `ansible` to check which user is performing the actions on the machine.