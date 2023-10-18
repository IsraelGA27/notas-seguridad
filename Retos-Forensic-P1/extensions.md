## extensions
## Objetivo
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Solución 

Vamos a buscar la firma del archivo ya que esta encriptado. Para eso vamos a utilizar el comando xxd.

![[Pasted image 20231018103312.png]]
Vemos que tiene una firma el inicio de png. Lo que tenemos que hacer es cambiar la extensión con el comando mv.

![[Pasted image 20231018103710.png]]
## Notas adicionales
![[Pasted image 20231018103513.png]]
## Referencias