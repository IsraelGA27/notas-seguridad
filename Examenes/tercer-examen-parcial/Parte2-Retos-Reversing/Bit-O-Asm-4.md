### Bit-O-Asm-4
## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
## Solución 
```shell
  
Si examinamos el archivo descargado, observaremos que se trata de un código breve escrito en lenguaje ensamblador.

<+0>: endbr64 
<+4>: push rbp 
<+5>: mov rbp,rsp 
<+8>: mov DWORD PTR [rbp-0x14],edi 
<+11>: mov QWORD PTR [rbp-0x20],rsi 
<+15>: mov DWORD PTR [rbp-0x4],0x9fe1a 
<+22>: cmp DWORD PTR [rbp-0x4],0x2710 
<+29>: jle 0x55555555514e <main+37> 
<+31>: sub DWORD PTR [rbp-0x4],0x65 
<+35>: jmp 0x555555555152 <main+41> 
<+37>: add DWORD PTR [rbp-0x4],0x65 
<+41>: mov eax,DWORD PTR [rbp-0x4] 
<+44>: pop rbp 
<+45>: ret

En la dirección de memoria [rbp-0x4], se asigna el valor 0x9fe1a. Luego, se compara si el contenido de la dirección de memoria [rbp-0x4] es menor o igual a 0x2710. Si esta comparación resulta falsa, se procede a restar 0x65 al valor almacenado en la dirección de memoria [rbp-0x4].

El resultado de estas operaciones nos dará la bandera buscada. En este caso, al evaluar la comparación, obtenemos el valor "False". Por lo tanto, al restar 0x65 al valor inicial, obtenemos la bandera:

>>> 0x9fe1a <= 0x2710 
False 
>>> int(0x9fe1a-0x65) 
654773

Flag:
	picoCTF{654773}
```
## Notas adicionales

## Referencias