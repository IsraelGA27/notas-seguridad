### transposition-trial
## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).
## Solución 
```shell
  
Si examinamos el mensaje cifrado, notaremos que este es su contenido. Para resolver este desafío, utilizaremos el siguiente sitio web [https://tholman.com/other/transposition/], donde ingresaremos nuestra cadena de mensaje. Después de eso, se nos pedirá un número de clave, que, según la pista proporcionada por el desafío, es 3.

Cuando presionemos el botón de (re)cargar tabla en la parte inferior, aparecerá una secuencia del 0 al 2.

0 1 2 Lo que debemos hacer es arrastrar el 2 a la primera posición, de manera que quede de la siguiente manera.

2 0 1 Esto nos dará como resultado lo siguiente.

The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
```
![[Pasted image 20231123070557.png]]
## Notas adicionales

## Referencias
https://tholman.com/other/transposition/