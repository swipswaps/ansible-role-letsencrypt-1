# Ansible role: letsencrypt

For use on shared hosting servers.

Installs LetsEncrypt, and makes a `/.well-known/acme-challenge` virtual directory available to other virtual hosts on the server, so they can all regsiter and renew LE SSL certificates.

## Requirements

NGINX or Apache 2 on Ubuntu 14.04 +, or Apache 2 on CentOS/RedHat 6

## Role Variables

```yaml
letsencrypt_webserver: [nginx|apache]
```
The brand of web server that's running on the server.


## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
         - { role: acromedia.letsencrypt }

## License

GPLv3

## Author Information

Acro Media Inc.
https://www.acromedia.com/
