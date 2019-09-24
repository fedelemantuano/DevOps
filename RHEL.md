# Hostname

```bash
hostnamectl set-hostname <chosen_hostname>
hostnamectl status
hostname -f    # fqdn
hostname -d    # domain
```

# hosts FILE
First 2 lines have to be left as they are:
```bash
[root@server ~]# cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

ip          fqdn   short
ip          fqdn   short
ip          fqdn   short
...
```

# Timezones
```bash
timedatectl                                 # Current Time and settings
timedatectl list-timezones | grep Europe    # Avaiable Timezones
timedatectl set-timezone Europe/Rome        # Set Timezone
```
