# ansible-librenms-ubuntu2204

This role installs and configures librems for Ubuntu 22.04 with Nginx and PHP-FPM.

This role supports configuring
* `ignore_mount`
* `ignore_mount_regexp`
* rrdcached
* poller threads
* baseurl and domain
* nets
* snmp (community, authname etc. at the moment only authPriv is
  `supported`)
* proxmox
* influxdb
* ldap

The default credentials for the installation are `admin` / `admin`.

RRDcached is setup on the server unless you remove `librenms_rrdcached` variable.

## Requirements

This role requires Ansible 2.7 or higher.

## Role Variables

See [defaults/main.yml](defaults/main.yml) for the documented role variables.
See also the distribution specific [vars](vars).

Mandatory variables are:
* `librenms_sql_db_password`

## Example Playbook

This playbook setups librenms.

    - hosts: apt_config
	  roles:
	    - role: ansible-librenms-ubuntu2204
    librenms_sql_db_password: librenmsdbpassword 
