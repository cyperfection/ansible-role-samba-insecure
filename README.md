# Ansible Role: Samba insecure

*DO NOT USE THIS ROLE!!! IT'S VERY INSECURE!!!*
Use only if you know what you are doing!

An Ansible Role that installs a Samba service in a very insecure way!

    security = user
    share modes = yes
    guest account = root
    map to guest = bad user

## Default share

The complete root filesystem will be shared (share name: system) writeable as root for guests! Very insecure!!!

## Configure shares

    samba_shares:
      - name: "foobar.vagrant"
        path: "/srv/sites/foobar.vagrant"
        comment: "foobar.vagrant as user www-data"
        guest_ok: "yes"
        read_only: "no"
        force_user: "www-data"
        force_group: "www-data"
