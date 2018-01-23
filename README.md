nginx
======

For setting up Nginx on an Ubuntu 14.04 or 16.04 server.


Requirements
------------
* Ubuntu

Role Variables
--------------
* letsencrypt_webserver: The webserver to use for letsencrypt

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: acromedia.nginx }

License
-------

BSD

Author Information
------------------

Acro Media Inc.
https://www.acromedia.com/
