
# Ansible Role: stunnel

## Description

Ansible role for install stunnel.

    Stunnel is a proxy designed to add TLS encryption functionality
    to existing clients and servers without any changes in the
    programs' code. Its architecture is optimized for security,
    portability, and scalability (including load-balancing),
    making it suitable for large deployments.
(https://www.stunnel.org/index.html)

It can be used to secure communication between Prometheus and his exporters.  
See: https://0x63.me/tls-between-prometheus-and-its-exporters/

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `debug_level` | 2 | logging verbosity |
| `ca_file` | ca.crt | Root certificate of CA used to sign client/server auth certificates |
| `cafile_location` | /etc/stunnel/tls | Directory in which stunnel store certificates |
| `pid_location` | /var/run/stunnel | Directory in which stunnel pidfile will be created |
| `log_location` | /var/log/stunnel | Directory in which stunnel logfile will be created |

### Playbook

Use it in a playbook as follows:

```yaml
- hosts: all
  roles:
    - stunnel
```

## Configuration notes
[stunnel online documentation](https://www.stunnel.org/docs.html)  
[stunnel configuration examples](https://www.stunnel.org/examples.html)

## License

This project is licensed under GNU GPL License. See [LICENSE](/LICENSE) for more details.

This role is inspired by https://github.com/cloudalchemy/ansible-mysqld-exporter  
Stunnel is free software created by [Michał Trojnara](http://mike.mirt.net/).  
Stunnel's website: https://www.stunnel.org/.  
And this is only wrap-up in Ansible role.
