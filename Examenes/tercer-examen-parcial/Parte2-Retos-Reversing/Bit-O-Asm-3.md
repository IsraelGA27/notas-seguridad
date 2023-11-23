### Bit-O-Asm-3
## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).
## Solución 
```shell
Analizando el archivo descargado veremos que es un código pequeño en ensamblador

<+0>: endbr64 
<+4>: push rbp 
<+5>: mov rbp,rsp 
<+8>: mov DWORD PTR [rbp-0x14],edi 
<+11>: mov QWORD PTR [rbp-0x20],rsi 
<+15>: mov DWORD PTR [rbp-0xc],0x9fe1a 
<+22>: mov DWORD PTR [rbp-0x8],0x4 
<+29>: mov eax,DWORD PTR [rbp-0xc] 
<+32>: imul eax,DWORD PTR [rbp-0x8] 
<+36>: add eax,0x1f5 
<+41>: mov DWORD PTR [rbp-0x4],eax 
<+44>: mov eax,DWORD PTR [rbp-0x4] 
<+47>: pop rbp <+48>: ret

En la dirección de memoria [rbp-0xc], se asigna el valor 0x9fe1a, mientras que en la dirección de memoria [rbp-0x8], se asigna el valor 0x4. Luego, el registro eax adquiere el valor almacenado en la memoria [rbp-0xc], que posteriormente se multiplica por el valor de la memoria [rbp-0x8] mediante la instrucción imul.

Finalmente, se suma 0x1f5 al resultado obtenido, lo cual representa la bandera buscada. La operación matemática correspondiente sería:

Flag = (0x9fe1a×0x4) + 0x1f5 = 2619997

>>> int((0x9fe1a*0x4)+0x1f5) 
>>> 261999

Flag:
	picoCTF{261999}

```
## Notas adicionales

## Referencias