### Bit-O-Asm-2
## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Solución 
```shell
Al examinar el archivo descargado, observamos que contiene un pequeño código en lenguaje ensamblador.

El contenido del archivo disassembler-dump0_b.txt es el siguiente:

<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret

Se puede notar que en el registro `eax` se encuentra una referencia a `[rbp-0x4]`, que a su vez hace referencia a la dirección de memoria `0x9fe1a`. Si utilizamos Python para convertir este valor a decimal, obtendremos la bandera:

>>> int(0x9fe1a)
654874

Flag:
	picoCTF{0x9fe1a}
```
## Notas adicionales

## Referencias