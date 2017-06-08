# ansible-playpen
Ansible Playbook Playpen

This is an area to develop playbooks I want to share publically, focused on
Red Hat Enterprise Linux 7 and Centos 7 environments

## Driving the playbooks

You'll need to specify your inventory `hosts` file that contains the host you wish to run the playbook against

```
ansible-playbook -i hosts playbook.yaml
```


## Playbooks

### grub_console.yaml

This playbook enables Serial Console for Grub and Serial Terminal post boot for
a RHEL / Centos / Fedora Libvirt VM Image

### unsafe_httpd.yaml

Recent versions of Apache don't allow hostnames to contain underscores.

- https://bugzilla.redhat.com/show_bug.cgi?id=1410130

This causes issues form some of my demo and sandbox environments.
The playbook uploads ```config/unsafe.conf``` containing the option

```
HttpProtocolOptions Unsafe
```

and then reloads the Apache environment to enable the change.
