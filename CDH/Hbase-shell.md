# Hbase Shell

Shell Start:
```bash
hbase shell                                            # to start the shell
```

### Namespaces
```bash
list_namespace
create_namespace '<NAMESPACE_NAME>'
drop_namespace '<NAMESPACE_NAME>'
```

### Permissions
List (help user_permission):
```bash
user_permission                                         # All namespaces
user_permission '@<NAMESPACE_NAME>'                     # Only for namespace
```

Grant (help grant):
```bash
grant 'admin', 'RWXCA'                                  # to admin with user admin (never needed, just an admin example)
grant 'hue', 'RWXC'                                     # to allow hue web to browse
grant 'namespaceX_admin', 'RWXCA', '@<NAMESPACE_NAME>'  # to allow autonomy in a namespace to a user
```

Revoke (help revoke):
```bash
revoke 'admin'                                           # tu revoke all global permissions to user admin
revoke 'namespaceX_admin', '@<NAMESPACE_NAME>'           # tu revoke all permissions on namespace to user namespaceX_admin
```
