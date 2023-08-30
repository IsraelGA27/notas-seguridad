# Bandit Level 9 → Level 10
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
```
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Solución 
```bash
bandit9@bandit:~$ pwd
/home/bandit9
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ ls -la
total 40
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit10 bandit9 19379 Apr 23 18:04 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ cat data.txt | strings -n 15
4========== the#
========== password
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ cat data.txt | strings -n 20
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas adicionales
strings - Despliega las cadenas que son imprimibles en archivos que no son solo cadenas.
Filtramos una cadena con varios signos de ==
tr -d "=": para quitar los guiones. 

## Referencias