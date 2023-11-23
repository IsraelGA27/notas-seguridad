### ASCII FTW
## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/507/asciiftw).
## Solución 
```shell
Después de descargar el archivo, es necesario otorgar permisos de ejecución.

┌──(israel㉿Kali-IS)-[~/Descargas] 
└─$ chmod +x asciiftw

Luego, se analiza el archivo con `gdb` y se cambia su formato de visualización para mostrar el método `main`.


┌──(israel㉿Kali-IS)-[~/Descargas]  
└─$ gdb asciiftw      
(No debugging symbols found in asciiftw)   
(gdb) set disassembly-flavor intel   
(gdb) disassemble main`

Dentro del código generado, se encuentra lo siguiente:

Dump of assembler code for function main:  
   0x0000000000001169 <+0>:     endbr64  
   0x000000000000116d <+4>:     push   rbp  
   0x000000000000116e <+5>:     mov    rbp,rsp  
   0x0000000000001171 <+8>:     sub    rsp,0x30  
   0x0000000000001175 <+12>:    mov    rax,QWORD PTR fs:0x28  
   0x000000000000117e <+21>:    mov    QWORD PTR [rbp-0x8],rax  
   0x0000000000001182 <+25>:    xor    eax,eax  
   0x0000000000001184 <+27>:    mov    BYTE PTR [rbp-0x30],0x70  
   0x0000000000001188 <+31>:    mov    BYTE PTR [rbp-0x2f],0x69  
   0x000000000000118c <+35>:    mov    BYTE PTR [rbp-0x2e],0x63  
   0x0000000000001190 <+39>:    mov    BYTE PTR [rbp-0x2d],0x6f  
   0x0000000000001194 <+43>:    mov    BYTE PTR [rbp-0x2c],0x43  
   0x0000000000001198 <+47>:    mov    BYTE PTR [rbp-0x2b],0x54  
   0x000000000000119c <+51>:    mov    BYTE PTR [rbp-0x2a],0x46  
   0x00000000000011a0 <+55>:    mov    BYTE PTR [rbp-0x29],0x7b  
   0x00000000000011a4 <+59>:    mov    BYTE PTR [rbp-0x28],0x41  
   0x00000000000011a8 <+63>:    mov    BYTE PTR [rbp-0x27],0x53  
   0x00000000000011ac <+67>:    mov    BYTE PTR [rbp-0x26],0x43  
   0x00000000000011b0 <+71>:    mov    BYTE PTR [rbp-0x25],0x49  
   0x00000000000011b4 <+75>:    mov    BYTE PTR [rbp-0x24],0x49  
   0x00000000000011b8 <+79>:    mov    BYTE PTR [rbp-0x23],0x5f  
   0x00000000000011bc <+83>:    mov    BYTE PTR [rbp-0x22],0x49  
   0x00000000000011c0 <+87>:    mov    BYTE PTR [rbp-0x21],0x53  
   0x00000000000011c4 <+91>:    mov    BYTE PTR [rbp-0x20],0x5f  
   0x00000000000011c8 <+95>:    mov    BYTE PTR [rbp-0x1f],0x45  
   0x00000000000011cc <+99>:    mov    BYTE PTR [rbp-0x1e],0x41  
   0x00000000000011d0 <+103>:   mov    BYTE PTR [rbp-0x1d],0x53  
   0x00000000000011d4 <+107>:   mov    BYTE PTR [rbp-0x1c],0x59  
   0x00000000000011d8 <+111>:   mov    BYTE PTR [rbp-0x1b],0x5f  
   0x00000000000011dc <+115>:   mov    BYTE PTR [rbp-0x1a],0x37  
   0x00000000000011e0 <+119>:   mov    BYTE PTR [rbp-0x19],0x42  
   0x00000000000011e4 <+123>:   mov    BYTE PTR [rbp-0x18],0x43  
   0x00000000000011e8 <+127>:   mov    BYTE PTR [rbp-0x17],0x44  
   0x00000000000011ec <+131>:   mov    BYTE PTR [rbp-0x16],0x39  
   0x00000000000011f0 <+135>:   mov    BYTE PTR [rbp-0x15],0x37  
   0x00000000000011f4 <+139>:   mov    BYTE PTR [rbp-0x14],0x31  
   0x00000000000011f8 <+143>:   mov    BYTE PTR [rbp-0x13],0x44

Este código se guarda en un nuevo archivo y se aplica el siguiente comando para obtener la bandera.

┌──(israel㉿Kali-IS)-[~/Descargas]  
└─$ cat numeros.txt | cut -d "," -f2 | xxd -r -p  
picoCTF{ASCII_IS_EASY_7BCD971D}

```
## Notas adicionales

## Referencias