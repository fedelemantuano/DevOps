# Hbase Shell

Shell Start:
```bash
hbase shell                                         # to start the shell
```


### Permissions
List (help user_permission):
```bash
user_permission                                     # All namespaces
user_permission '@namespace'                        # Only for namespace
```

Grant (help grant):
```bash
grant 'admin', 'RWXCA'                              # to admin with user admin (never needed, just an admin example)
grant 'hue', 'RWXC'                                 # to allow hue web browse
grant 'namespaceX_admin', 'RWXCA', '@namespaceX'    # to allow autonomy in a namespace to a user
```

Revoke (help revoke):
```bash
revoke 'admin'                                      # to admin with user admin (never needed, just an admin example)
revoke 'namespaceX_admin', '@namespaceX'            # to allow autonomy in a namespace to a user
```
