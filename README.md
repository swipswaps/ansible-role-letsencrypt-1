# Ansible role: letsencrypt

For use on shared hosting servers. The role:
- Installs LetsEncrypt,
- Makes a `/.well-known/acme-challenge` virtual directory available to all virtual hosts on the server (including the default site), so all sites can regsiter and renew LE SSL certificates,
- Overwrites the default site config (after backing up the original), so it can be served with a valid LetsEncrypt certificate instead of the default snakeoil certificate.

As an added bonus, after this role is installed, you won't need to create new virtual hosts to register new LetsEncrypt certificates. Since the default site acts as a catch-all, as long as DNS points at your server, you can register a certificate for that name.

## Requirements

NGINX or Apache 2 on Ubuntu >= 14.04 +, or Apache 2 on CentOS/RedHat >= 6

## Role Variables

- **letsencrypt_webserver**

  The brand of web server that's installed on the server. Defaults to `nginx`. Can be either `nginx` or `apache`.

- **http_port**

  Defaults to `80`. Change it to something else if you're installing Varnish in front of your web service.

- **https_port**

  Defaults to `443`. Change it to something else if you're installing Varnish in front of your web service.


## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: acromedia.letsencrypt
          vars:
            letsencrypt_webserver: nginx
            http_port: 80
            https_port: 443


## License

GPLv3

## Author Information

Acro Media Inc.
https://www.acromedia.com/
