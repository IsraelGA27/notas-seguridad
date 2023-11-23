## Wave a flag
## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm) has extraordinarily helpful information...
## Datos de acceso al nivel
## Solución 
```shell
israelga-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm
--2023-09-25 16:40:37--  https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                                       100%[=======================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2023-09-25 16:40:37 (141 MB/s) - 'warm' saved [10936/10936]

israelga-picoctf@webshell:~$ chmod +x warm
israelga-picoctf@webshell:~$ -h
-bash: -h: command not found
israelga-picoctf@webshell:~$ ls
README.txt  flag  warm
israelga-picoctf@webshell:~$ warm
-bash: warm: command not found
israelga-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
israelga-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}
```
## Notas adicionales
Podemos descargar un archivo en la terminal usando wget, adjuntando la dirección de enlace del archivo a descargar.
Para cambiar los permisos de un archivo en Linux se usa chmod.
## Referencias