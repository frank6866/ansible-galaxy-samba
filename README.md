samba
==============

samba deployment.


Role Variables
--------------
No required vars, the optional var as follows:

```
samba_port: 11211
samba_user: samba
samba_maxconn: 1024
samba_cachesize: 64
samba_ipv4_address: 0.0.0.0
```


Example Playbook
----------------

```
- hosts: samba
  become: true
  roles:
    - /path/to/samba
```


License
-------

MIT

