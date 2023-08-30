# Bandit Level 10 → Level 11
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data.
## Datos de acceso al nivel
```
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
## Solución 
```bash
bandit10@bandit:~$ cd ~
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```
## Notas adicionales
base64: 
	Es una utilidad en sistemas Unix y similares que se utiliza para codificar y decodificar datos en formato base64.
El formato base64 es una forma de representar datos binarios utilizando caracteres imprimibles, lo que lo hace útil para transferir o almacenar datos en entornos que no manejan bien los datos binarios, como en correos electrónicos o en archivos de texto.
Cuando se usa el comando `base64` en modo codificación, toma datos binarios y los convierte en una cadena de caracteres que consta de caracteres alfanuméricos y algunos caracteres especiales. Esto es útil cuando deseas transmitir o almacenar datos binarios en un formato de texto plano. Por otro lado, en modo decodificación, toma una cadena de caracteres en formato base64 y la convierte de nuevo a su forma binaria original.

El archivo `data.txt` contiene datos codificados en base64. Usar el comando `base64 -d` en ese archivo decodificará los datos y revelará el contenido original, que en este caso es la contraseña para el siguiente nivel del desafío.
## Referencias
[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)