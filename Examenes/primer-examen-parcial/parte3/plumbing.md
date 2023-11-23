## plumbing
## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.
## Solución 
```shell
Prueba inicial dando: 
israelga-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
Again, I really don't think this is a flag
This is defintely not a flag
This is defintely not a flag
Not a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
This is defintely not a flag

Prueba usando grep:
israelga-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep pico
picoCTF{digital_plumb3r_06e9d954}

```
## Notas adicionales
Uso de grep para filtrar la palabra clave "pico".
## Referencias