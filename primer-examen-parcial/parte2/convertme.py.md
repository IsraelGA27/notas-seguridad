## convertme.py
## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
## Solución 
```shell
israelga-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2023-09-30 00:10:56--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.71, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                               100%[=======================================================================================================================================>]   1.16K  --.-KB/s    in 0s      

2023-09-30 00:10:56 (459 MB/s) - 'convertme.py' saved [1189/1189]

israelga-picoctf@webshell:~$ ls
README.txt  convertme.py
israelga-picoctf@webshell:~$ python convertme.py
If 81 is in decimal base, what is it in binary base?
Answer: 1010001
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
israelga-picoctf@webshell:~$ 
```
## Notas adicionales
## Referencias
https://www.rapidtables.com