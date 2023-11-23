### GDB baby step 1
## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).
## Solución 
```shell
Una vez que hemos descargado el archivo, otorgamos los permisos de ejecución mediante el comando:

chmod +x debugger0_a

Posteriormente, abrimos el archivo con GDB y ejecutamos los siguientes comandos. El primero se encarga de mostrar el código en formato Intel, mientras que el segundo nos presenta la función principal (main):

gdb debugger0_a
(gdb) set disassembly-flavor intel
(gdb) disassemble main

En la función main, se observa el siguiente código:

   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   rbp
   0x000000000000112e <+5>:     mov    rbp,rsp
   0x0000000000001131 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000001134 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000001138 <+15>:    mov    eax,0x86342
   0x000000000000113d <+20>:    pop    rbp
   0x000000000000113e <+21>:    ret

Se puede observar que el valor asignado a `eax` es 0x86342. Al convertir este valor a decimal, obtenemos la bandera buscada:

>>> int(0x86342)
549698

Flag:
	picoCTF{549698}

```
## Notas adicionales

## Referencias