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


# install executables

```bash
mv ./<exec> /usr/local/bin/
chmod 755 /usr/local/bin/<exec>
```

# System Info

```bash
less /proc/cpuinfo      # CPU INFO
free -m (-m MB, -g GB)  # RAM INFO
```

# Find Files

```bash
find / -name <FILE_NAME_EXPR> 2>&1 | grep -v "Permission denied"
```
