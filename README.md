# ansible-role-sshd

Flexible role to configure OpenSSH server.

# Role Variables

```yaml
sshd_config_file: '/etc/ssh/sshd_config'
```

Each configuration key in `sshd_config(5)` can be set with the role variable `sshd_[key]`, where `[key]` is the key name in camelcase, e.g.

```yaml
sshd_DisableForwarding: "yes"
# sets DisableForwarding yes
```

Most keys take first value encountered, but there are exceptions. These keys can all be listed more than once:
**AcceptEnv, AllowGroups, AllowUsers, DenyGroups, DenyUsers, HostKey, ListenAddress, Match, Port**.

If you import the role more than once, you can "stack" these keys by placing the config in different files under `/etc/sshd_config.d/` with `sshd_config_file`.
