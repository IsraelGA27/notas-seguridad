# Bandit Level 13 → Level 14
# Level X
## Objetivo
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on
## Datos de acceso al nivel
```
ssh bandit13@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: bandit13

wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```
## Solución 
```bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit13/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit13/.ssh/known_hosts).

bandit14@bandit:~$ ls
bandit14@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .ssh
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
## Notas adicionales
El comando `ssh -i sshkey.private` se utiliza para iniciar una conexión SSH a un servidor remoto utilizando una clave privada específica en lugar de una contraseña para la autenticación
- `ssh`: Este es el comando principal que se utiliza para iniciar una sesión SSH.
    
- `-i sshkey.private`: Esta parte del comando especifica la clave privada que se utilizará para la autenticación. La opción `-i` se utiliza para indicar la ubicación de la clave privada. En este caso, "sshkey.private" debe ser reemplazado por la ubicación y el nombre de archivo de su clave privada SSH. La clave privada se utiliza para demostrar que usted es el propietario legítimo de la clave pública correspondiente almacenada en el servidor remoto.

La secuencia completa del comando permitirá iniciar una sesión SSH utilizando la clave privada especificada para autenticarse en el servidor remoto. Esto es útil cuando se desea una autenticación más segura y se evita el uso de contraseñas. Por favor, asegúrese de que la clave privada especificada tenga los permisos adecuados para garantizar la seguridad de la autenticación.
## Referencias
[SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)