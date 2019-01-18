# Disk space

```bash
df -h                 # free space
du -h --max-depth=1   # disck usage at current level
du -h --max-depth=1 2> /dev/null    # remove stderr Permission denied
```

# Ssh Keys

```bash
ssh-keygen -t rsa -b 4096 -f .ssh/id_rsa_XYZ
```
