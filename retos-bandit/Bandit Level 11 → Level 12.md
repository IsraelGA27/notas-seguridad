# Bandit Level 11 → Level 12
## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
```
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
## Solución 
```bash
bandit11@bandit:~$ pwd
/home/bandit11
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit12 bandit11   49 Apr 23 18:04 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit11@bandit:~$ cd ~
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```
## Notas adicionales
tr - Es una utilidad en sistemas Unix y similares que se utiliza para realizar la traducción o transformación de caracteres en un flujo de texto. Puede ser utilizado para reemplazar, eliminar o transformar caracteres en un archivo o en la entrada de texto que se le proporciona.

Algunas de las operaciones comunes que se pueden realizar con el comando `tr` incluyen:

- Reemplazar caracteres en un flujo de texto con otros caracteres.
- Eliminar caracteres específicos de un flujo de texto.
- Transformar caracteres de minúsculas a mayúsculas o viceversa.
- Realizar operaciones de transliteración (por ejemplo, convertir caracteres acentuados en sus equivalentes no acentuados).
`tr` se utiliza para realizar la decodificación ROT13, donde los caracteres del alfabeto son reemplazados por los caracteres que se encuentran 13 posiciones adelante. El comando toma un conjunto original de caracteres (las letras del alfabeto en mayúsculas y minúsculas) y los reemplaza por el conjunto de caracteres resultante después de la rotación de 13 posiciones. Esto permite descifrar el mensaje que ha sido codificado en ROT13.
## Referencias
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)