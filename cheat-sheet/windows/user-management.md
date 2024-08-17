# User Management

{% code title="Add your user to admins" overflow="wrap" %}
```bash
net user <username> <password> /add

net localgroup administrators <username> /add
```
{% endcode %}
