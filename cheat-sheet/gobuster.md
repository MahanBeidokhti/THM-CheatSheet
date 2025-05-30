---
description: used for locating locations on a sever
---

# Gobuster

{% code title="Basic" %}
```sh
gobuster dir -u http://10.10.108.64:3333 -w 
```
{% endcode %}



***

### flags :&#x20;

<table><thead><tr><th width="198">flag</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>-e</td><td>Print the full URLs in your console</td><td></td></tr><tr><td>-u</td><td>The target URL</td><td></td></tr><tr><td>-w</td><td>Path to your wordlist</td><td></td></tr><tr><td>-U and -P</td><td>Username and Password for Basic Auth</td><td></td></tr><tr><td>-p</td><td>Proxy to use for requests</td><td></td></tr><tr><td>-c</td><td>Specify a cookie for simulating your auth</td><td></td></tr></tbody></table>
