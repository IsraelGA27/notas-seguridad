# Bandit Level 14 → Level 15
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel
```
ssh bandit14@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```
## Solución 
```
bandit14@bandit:~$ ls
bandit14@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .ssh
bandit14@bandit:~$ nc localhost 30000

Wrong! Please enter the correct current password
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Notas adicionales
`nc` (netcat)
- `nc`: Es el comando para netcat, una utilidad de red que puede ser utilizada para crear conexiones de red, enviar y recibir datos a través de sockets, y realizar otras tareas relacionadas con la red.
    
- `localhost`: En este contexto, "localhost" se refiere a la dirección IP de loopback, que siempre apunta a la propia máquina en la que se está ejecutando el comando. En otras palabras, se está intentando establecer una conexión con un servicio que se ejecuta en la misma máquina en la que se ejecuta el comando.
    
- `30000`: Es el número de puerto al que se está intentando conectar. En este caso, se está intentando conectar al servicio que escucha en el puerto 30000 en la máquina local.
## Referencias
- [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (Not completely accurate, but good enough for beginners)
- [IP Addresses](http://computer.howstuffworks.com/web-server5.htm)
- [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
- [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
- [Ports](http://computer.howstuffworks.com/web-server8.htm)
- [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))