## Obedient Cat
## Objetivo
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag).
Hints:
	Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
	To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag`
	$ man cat
## Solución 
```shell
israelga-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
--2023-09-25 16:44:00--  https://mercury.picoctf.net/static/217686fc11d733b80be62dcfcfca6c75/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag.1'

flag.1                                                     100%[=======================================================================================================================================>]      34  --.-KB/s    in 0s      

2023-09-25 16:44:01 (14.1 MB/s) - 'flag.1' saved [34/34]

israelga-picoctf@webshell:~$ ls
README.txt  flag  flag.1  warm
israelga-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_b5aeb3dd}
israelga-picoctf@webshell:~$
```
## Notas adicionales
Uso de cat con el archivo flag.
## Referencias