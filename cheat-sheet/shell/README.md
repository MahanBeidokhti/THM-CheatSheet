---
description: >-
  different types of shell attacks and getting access of the attacking machine's
  shell
---

# Shell

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td>NetCat Shell (nc)</td><td></td><td></td><td><a href="../../.gitbook/assets/1.png">1.png</a></td><td><a href="netcat-nc.md">netcat-nc.md</a></td></tr><tr><td>Socat Shell</td><td></td><td></td><td><a href="../../.gitbook/assets/2.png">2.png</a></td><td><a href="socat/">socat</a></td></tr></tbody></table>



## Basics :

### Reverse shell

1. you run a listener on your machine&#x20;
2. you run a connect back on the target machine (using ssh or...)&#x20;
3. you got a shell on your machine

### Bind shell

1. you run a port oppener command on the target machine(using ssh or ...)
2. you run a connect command on your machine (like `nc <ip> <port>`)[^1]
3. you got a shell on your machine&#x20;



[^1]: 
