ansible deploy samba role
=========================

This role is uesd to deploy samba server.



Inventory file demo
-------------------
```
samba-1 ansible_ssh_host=10.10.10.10 ansible_ssh_port=2233 ansible_ssh_user=root

[samba]
samba-1

```


Role Variables
--------------
No required vars, the optional var as follows:

The default group name of samba user is **group_samba**, you can change it by setting **samba_group** variable:

> samba_group: sambas


If you wan to add user and config path for user, you can set the following variable:

```
samba_user_config:
  - name: suse
    password: change_me
    local_path: /share
    remote_show_name: suse
    comment: path /share on server
    state: present
```


Example Playbook
----------------

```
- hosts: samba
  become: true
  roles:
    - /path/to/samba
```


Verify on client
----------------
Assuming we use CentOS7.

Install client:

> yum install cifs-utils

Create a directory before mounting:

> mkdir smb_mount

Mount remote path to the directory we create:

> mount.cifs //10.10.10.10/frank smb_mount/ -o user=suse,pass=change_me


**Enjoy it!**


License
-------

MIT

