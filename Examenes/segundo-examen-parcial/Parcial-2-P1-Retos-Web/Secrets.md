### Secrets
## Objetivo
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:65455/).
## Solución 
```shell
Necesitamos examinar el código web y notamos un enlace con la etiqueta href="vendor/bootstrap/css/bootstrap.min.css". Lo incorporamos en la ruta [http://saturn.picoctf.net:65455/secret/](http://saturn.picoctf.net:65455/secret/).

Luego, revisamos el código fuente y encontramos otra URL. La añadimos de manera que la URL final sea la siguiente: [http://saturn.picoctf.net:65455/secret/hidden/](http://saturn.picoctf.net:65455/secret/hidden/).
```
![[Pasted image 20231103022505.png]]
En esta dirección web se encuentra un inicio de sesión que no es accesible. Como resultado, exploramos el código fuente y descubrimos un segundo enlace, "superhidden/login.css", al que agregamos al camino para que se vea de la siguiente manera: "view-source:[http://saturn.picoctf.net:65455/secret/hidden/superhidden/](http://saturn.picoctf.net:65455/secret/hidden/superhidden/)".
![[Pasted image 20231103022637.png]]
## Notas adicionales
## Referencias