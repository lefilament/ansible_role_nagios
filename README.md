nagios
=========

This role deploys Nagios with Nginx. This role is not maintained anymore, use docker_nagios instead.

Requirements
------------

None.

Role Variables
--------------

This role needs only 2 variables for deploying Odoo :
* nagios_url: URL for accessing Nagios
* default_maintenance_email: e-mail used to generate Let's Encrypt SSL certificate

Dependencies
------------

This role deploys a Nagios server for monitoring all hosts defined in inventory. It then makes use of variables defined in these groups, for instance :
* odoo_url (for group odoo_server)
* cloud_url (for group owncloud_server)

Example Playbook
----------------

    - hosts: nagios_server
      become: true
      roles:
      - { role: nagios, tags: nagios }
      vars:
      - { nagios_url: "nagios.example.org" }

License
-------

AGPL-3

Author Information
------------------

Le Filament (https://le-filament.com)
