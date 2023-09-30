## Glitch Cat
## Objetivo
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 49700`
## Solución 
```shell
israelga-picoctf@webshell:~$ nc saturn.picoctf.net 49700
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'

israelga-picoctf@webshell:~$ python -c 'print(chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65))'
a4392d2e
israelga-picoctf@webshell:~$ 

= picoCTF{gl17ch_m3_n07_a4392d2e}
```
## Notas adicionales
`python -c` se utiliza para ejecutar una o varias líneas de código de Python directamente desde la línea de comandos, en lugar de escribir el código en un archivo Python separado y luego ejecutar ese archivo.
## Referencias