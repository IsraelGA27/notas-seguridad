# Bandit Level 8 → Level 9
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
```
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Solución 
```bash
bandit8@bandit:~$ pwd
/home/bandit8
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```
## Notas adicionales
Piping: Redirigir una salida
sort: comando que ordena líneas de texto, escribienddola concatenada (cat data.txt | sort)
uniq: 
	-u: Solo muestra la que son únicas. (Para funcionar espera una entrada ordenada -usa el sort-)
	-c: Cuenta cuantas veces se repite una linea.
	-d: Solo muestra las que se repiten
## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)