# ansible-role-sshd

Flexible role to configure OpenSSH sshd server.

# Role Variables

```yaml
sshd_config_file: '/etc/ssh/sshd_config'
```

Each configuration key in `sshd_config(5)` can be set with the role variable `sshd_[key]`, where `[key]` is the key name in camelcase, e.g.

```yaml
sshd_DisableForwarding: "yes"
# sets DisableForwarding yes
```

# Limitations

Currently only one instance of each key is allowed and they are listed in alphabetical order.

This has consequences for keys that may appear more than once, and keys in which the order matters, such as
**AcceptEnv, AllowGroups, AllowUsers, DenyGroups, DenyUsers, HostKey, ListenAddress, Match, Port**.

