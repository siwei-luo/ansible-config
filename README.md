# Ansible Configuration Playbooks

Just some (opinionated) Arch Linux configuration. Primarily targets Intel ThinkPads but should work with other
laptops too.

## Playbooks

* `play.yaml` is the main playbook which should be either executed in the chroot in the live installation environment
  or later on the running machine.
* `play-preflight.yaml` is the playbook which only needed to be executed once **before** chrooting. It has pre-requisites:
  * root already mounted in `/mnt`
    * (optional) with any other partitions mounted as well below `/mnt/` - THIS IS UNTESTED THOUGH
  * network connection established
  * Ansible installed `pacman -S ansible`

### Run Playbook
```shell
ansible-playbook play.yaml
```