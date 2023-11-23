## Static ain't always noise
## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!
## Solución 
```shell
israelga-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
--2023-09-25 17:07:23--  https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                                     100%[=======================================================================================================================================>]   8.18K  --.-KB/s    in 0s      

2023-09-25 17:07:23 (231 MB/s) - 'static' saved [8376/8376]

israelga-picoctf@webshell:~$ ls
README.txt  static
 israelga-picoctf@webshell:~$ ls -la
total 40
drwxr-xr-x 2 israelga-picoctf israelga-picoctf  128 Sep 25 17:07 .
drwxr-xr-x 3 root             root               30 Sep 25 16:29 ..
-rw------- 1 israelga-picoctf israelga-picoctf    7 Sep 25 16:30 .bash_history
-rw-r--r-- 1 israelga-picoctf israelga-picoctf  220 Sep 25 16:29 .bash_logout
-rw-r--r-- 1 israelga-picoctf israelga-picoctf 3771 Sep 25 16:29 .bashrc
-rw-r--r-- 1 israelga-picoctf israelga-picoctf  807 Sep 25 16:29 .profile
-rw-rw-r-- 1 israelga-picoctf israelga-picoctf  167 Sep 25 16:34 .wget-hsts
-rw-r--r-- 1 root             root             4443 Sep 25 16:40 README.txt
-rw-rw-r-- 1 israelga-picoctf israelga-picoctf 8376 Mar 16  2021 static
israelga-picoctf@webshell:~$ file static
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=33934f7b8aea8e359749ed57dca4cd26d6059acf, not stripped
israelga-picoctf@webshell:~$ chmod +x static
israelga-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
israelga-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
israelga-picoctf@webshell:~$ strings static | grep pic 
picoCTF{d15a5m_t34s3r_1e6a7731}

```
## Notas adicionales
Se uso chmod +x para darle permisos a static.
## Referencias