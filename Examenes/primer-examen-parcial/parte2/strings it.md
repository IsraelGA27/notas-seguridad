## strings it
## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?
## Solución 
```shell
israelga-picoctf@webshell:~$ ls
README.txt  strings
israelga-picoctf@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=047a5079a5f563cd0e540d28f42a37161093ffda, not stripped
israelga-picoctf@webshell:~$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_827aee91}
israelga-picoctf@webshell:~$ 
```
## Notas adicionales
## Referencias