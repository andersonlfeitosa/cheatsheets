## Linux Administration 


This is a little cheatsheet about [Linux](https://linux.org).

### Creating a Swap File 64MB
```
dd if=/dev/zero of=/swapfile bs=1024 count=65536
chmod 0600 /swapfile
mkswap /swapfile
swapon /swapfile
```

To enable it at boot time, edit /etc/fstab to include the following entry:
```
/swapfile          swap            swap    defaults        0 0
```
