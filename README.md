# centos7-os-ansible
This container has ansible preinstalled (latest version available from epel-release on latest tag) and contains and runs systemd/dbus at strtup to emulate a full CentoOS system.

This is for use with molecule to test Ansible roles that are meant to run against full systems and not containers.

Molecule platform config to run this containere properly:
```
platforms:
  - name: random_name
    image:  bandit145/centos7-os-ansible
    privileged: true
    pre_build_image: true
    override_command: False
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
```
