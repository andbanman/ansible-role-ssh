# ansible-role-openssh

Flexible role to configure OpenSSH server.

# Role Variables

```yaml
openssh_sshd_config_file: '/etc/ssh/sshd_config'
```

Each configuration key in `sshd_config(5)` can be set with the role variable `openssh_[key]`, where `[key]` is the key name in camelcase, e.g.

```yaml
openssh_DisableForwarding: "yes"
# sets DisableForwarding yes
```

Most keys take first value encountered, but there are exceptions. The keys are
**AcceptEnv, AllowGroups, AllowUsers, DenyGroups, DenyUsers, HostKey, ListenAddress, Match, Port**.

If you import the role more than once, you can "stack" these keys by placing the config in different files under `/etc/sshd_config.d/` with `openssh_sshd_config_file`.
