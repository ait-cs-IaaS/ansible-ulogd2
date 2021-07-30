ulogd2
=========

This role can be used to install and configure the ulogd2 logging daemon.


Role Variables
--------------

- `ulogd2_conf_template`: The template file to use for the ulogd2 config (default=templates/ulogd.conf.j2)
- `ulogd2_conf_dest`: The file destination for the config file (default=/etc/ulog.conf)
- `ulogd2_user`: The user to use for the daemon (default=ulog)
- `ulogd2_logfile`: The logfile for status messages (default=syslog)
- `ulogd2_loglevel`: The ulogd log level (default=3)
- `ulogd2_lib_dir`: The ulogd library directory containing the plugins (default=/usr/lib/x86_64-linux-gnu/ulogd/)
- `ulogd2_stack`: The ulogd plugin stack configuration (as a list)
- `ulogd2_plugins`: List of ulogd plugins to activate
- `ulogd2_global_options`: Additional configuration options for the `global` section (dict of values)
- `ulogd2_config`: Additional configuration sections for the config file. As dict of dicts e.g.,
- 
```yaml
ulogd2_config:
  emu1:
    file: /var/log/ulog/syslogemu.log
    sync: 1
```
-->
```toml
[emu1]
file="/var/log/ulog/syslogemu.log"
sync=1
```


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
    - hosts: servers
      roles:
         - role: ulogd2
           ulogd2_loglevel: 7
```

License
-------

GPL-3.0

Author Information
------------------

Maximilian Frank
