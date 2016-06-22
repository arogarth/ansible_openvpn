Role Name
=========

Currently only for Ubuntu and Debian OS.

This role installs openvpn from apt repository and configures the server,
creates client configurations and certificates.

Requirements
------------

Nothing

Role Variables
--------------

Have a look at default/main.yml

Dependencies
------------

No Dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: all
  become: yes
  vars:
    openvpn_clients:
      - client: "client1"
        email: "client1@openvpn.local"
      - client: "client2"
        email: "client2@openvpn.local"
      rsa:
        key_directory: "/etc/openvpn/keys"
        key_country: "DE"
        key_province: "HE"
        key_city: "Frankfurt"
        key_org: "openvpn"
        key_email: "admin@openvpn.local"
        key_ou: "OpenVPN Organization Unit"
        key_name: "EasyRSA"
        key_cn: "CommonName"
        key_size: 2048
        key_expire: 3650
        ca_expire: 3650

  roles:
    - role: arogarth.openvpn


```

License
-------

MIT
