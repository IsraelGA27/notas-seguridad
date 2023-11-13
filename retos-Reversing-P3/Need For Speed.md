### Need For Speed
## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed).
## Solución 
```shell
Al examinar el archivo descargado, observaremos que se trata de un archivo ejecutable, por lo tanto, debemos asignarle los permisos adecuados.

file need-for-speed 
# need-for-speed: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b4b1e824082c140091043151ab990149efa44806, not stripped

chmod +x need-for-speed 

Al ejecutar el archivo, notaremos que al inicio se mencionará que se está generando la clave, pero antes de completarse este proceso, el tiempo se agotará y la ejecución del programa finalizará.

```
![[Pasted image 20231113035535.png]]
```shell
Podemos emplear la utilidad gdb.

┌──(israel㉿Kali-IS)-[~/Descargas]  
└─$ gdb need-for-speed  
GNU gdb (Debian 13.2-1) 13.2  
Copyright (C) 2023 Free Software Foundation, Inc.  
License GPLv3+: GNU GPL version 3 or later <[http://gnu.org/licenses/gpl.html](http://gnu.org/licenses/gpl.html)>  
This is free software: you are free to change and redistribute it.  
There is NO WARRANTY, to the extent permitted by law.  
Type "show copying" and "show warranty" for details.  
This GDB was configured as "x86_64-linux-gnu".  
Type "show configuration" for configuration details.  
For bug reporting instructions, please see:  
<[https://www.gnu.org/software/gdb/bugs/](https://www.gnu.org/software/gdb/bugs/)>.  
Find the GDB manual and other documentation resources online at:  
    <[http://www.gnu.org/software/gdb/documentation/](http://www.gnu.org/software/gdb/documentation/)>.  
  
For help, type "help".  
Type "apropos word" to search for commands related to "word"...  
Reading symbols from need-for-speed...  
(No debugging symbols found in need-for-speed)  
(gdb) set disassembly-flavor intel  
(gdb) disassemble main  
Dump of assembler code for function main:  
   0x000000000000091a <+0>:     push   rbp  
   0x000000000000091b <+1>:     mov    rbp,rsp  
   0x000000000000091e <+4>:     sub    rsp,0x10  
   0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi  
   0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi  
   0x0000000000000929 <+15>:    mov    eax,0x0  
   0x000000000000092e <+20>:    call   0x8d8 <header>  
   0x0000000000000933 <+25>:    mov    eax,0x0  
   0x0000000000000938 <+30>:    call   0x82f <set_timer>  
   0x000000000000093d <+35>:    mov    eax,0x0  
   0x0000000000000942 <+40>:    call   0x87d <get_key>  
   0x0000000000000947 <+45>:    mov    eax,0x0  
   0x000000000000094c <+50>:    call   0x8ac <print_flag>  
   0x0000000000000951 <+55>:    mov    eax,0x0  
   0x0000000000000956 <+60>:    leave  
   0x0000000000000957 <+61>:    ret  
End of assembler dump.  
(gdb) break main  
Breakpoint 1 at 0x91e  
(gdb) run  
Starting program: /home/israel/Descargas/need-for-speed  
[Thread debugging using libthread_db enabled]  
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".  
  
Breakpoint 1, 0x000055555540091e in main ()  
(gdb) disassemble main  
Dump of assembler code for function main:  
   0x000055555540091a <+0>:     push   rbp  
   0x000055555540091b <+1>:     mov    rbp,rsp  
=> 0x000055555540091e <+4>:     sub    rsp,0x10  
   0x0000555555400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi  
   0x0000555555400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi  
   0x0000555555400929 <+15>:    mov    eax,0x0  
   0x000055555540092e <+20>:    call   0x5555554008d8 <header>  
   0x0000555555400933 <+25>:    mov    eax,0x0  
   0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>  
   0x000055555540093d <+35>:    mov    eax,0x0  
   0x0000555555400942 <+40>:    call   0x55555540087d <get_key>  
   0x0000555555400947 <+45>:    mov    eax,0x0  
   0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>  
   0x0000555555400951 <+55>:    mov    eax,0x0  
   0x0000555555400956 <+60>:    leave  
   0x0000555555400957 <+61>:    ret  
End of assembler dump.  
(gdb) call (int) get_key()  
Creating key...  
Finished  
$1 = 9  
(gdb) call (int) print_flag()  
Printing flag:  
PICOCTF{Good job keeping bus #24c43740 speeding along!}  
$2 = 56  
(gdb)

```
## Notas adicionales
Flag: PICOCTF{Good job keeping bus #190ca38b speeding along!}
## Referencias