# Linux

## files :&#x20;

* `/etc/shadow  'world-writable'` : **users passes hashes**&#x20;
* `/etc/passwd  'world-readable'` : **users information**
* `/etc/crontab 'world-writable'` : **Cron table files**



## functions :&#x20;

* **hash password** **(/etc/shadow file)** : `mkpasswd -m sha-512 newpasswordhere`
* **hash password (/etc/passwd file)** : `openssl passwd newpasswordhere`
* **shared libraries are used by the program** : `'ldd' /usr/sbin/apache2`
* **Locate a file** : `locate <FILE>`
* **output stderr and stdout to std out** : `2>&1`
* **observe and record any syscalls of a command** : `strace`
* **rewrite a file functionality** : `function /usr/sbin/service { /bin/bash -p; }`\
  `export -f /usr/sbin/service`
* **locate a package** : `which <PACKAGE>`
* **search for a file** : `find /path -iname filename`
* **mount a shared folder** : `mount -o rw,vers=3 10.10.10.10:/tmp /tmp/nfs`
*



## Dictionary



<table><thead><tr><th width="178">Word</th><th>Meaning</th></tr></thead><tbody><tr><td>cron jobs</td><td>programs or scripts which users can schedule to run at specific times or intervals</td></tr><tr><td>SUID</td><td>The Unix and Linux access rights flags setuid and setgid allow users to run an executable with the file system permissions of the executable's owner or group respectively and to change behaviour in directories</td></tr></tbody></table>
