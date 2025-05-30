---
description: used to discover hosts and services on a computer network
---

# NMAP

{% code title="Basic" %}
```bash
nmap <flags> <RHOST>

# usually :
nmap -sT -sC -sV -vv -p <PORT-DOMAIN> <IP>
```
{% endcode %}



***

### Flags

<table><thead><tr><th width="174" align="center">Flag</th><th align="center">Description</th></tr></thead><tbody><tr><td align="center">-sV</td><td align="center">Attempts to determine the version of the services running</td></tr><tr><td align="center">-p or -p-</td><td align="center">Port scan for port or scan all ports</td></tr><tr><td align="center">-Pn</td><td align="center">Disable host discovery and scan for open ports</td></tr><tr><td align="center">-A</td><td align="center">Enables OS and version detection, executes in-build scripts for further enumeration</td></tr><tr><td align="center">-sC</td><td align="center">Scan with the default Nmap scripts</td></tr><tr><td align="center">-v</td><td align="center">Verbose mode</td></tr><tr><td align="center">-sU</td><td align="center">UDP port scan</td></tr><tr><td align="center">-sS</td><td align="center">TCP SYN port scan</td></tr></tbody></table>
