### GDB baby step 2
## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).
## Solución 
```shell
Luego de descargar el archivo, otorgamos permisos de ejecución mediante el comando `chmod +x debugger0_b`. 
Posteriormente, abrimos el archivo con GDB y aplicamos los siguientes comandos. El primero se encarga de mostrar el código en estructura Intel, mientras que el segundo nos presenta la clase `main`:

gdb debugger0_b
(gdb) set disassembly-flavor intel
(gdb) disassemble main

La clase `main` contiene las siguientes instrucciones:

0x0000000000401106 <+0>:     endbr64
0x000000000040110a <+4>:     push   rbp
0x000000000040110b <+5>:     mov    rbp,rsp
0x000000000040110e <+8>:     mov    DWORD PTR [rbp-0x14],edi
0x0000000000401111 <+11>:    mov    QWORD PTR [rbp-0x20],rsi
...

Después de esto, utilizamos los siguientes comandos:

(gdb) break main
(gdb) layout asm
(gdb) run


Al ejecutar el último comando, se abrirá una nueva ventana en la que ingresamos los siguientes comandos:

break *0x401142
c
info registers rip
print/d $eax

El último comando imprime el valor de la bandera, que en este caso es 307019. Con esto, solo queda dar formato a la bandera.

Flag:
	picoCTF{307019}
```
## Notas adicionales

## Referencias