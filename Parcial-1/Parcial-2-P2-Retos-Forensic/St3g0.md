### St3g0
## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/215/pico.flag.png)
## Solución 
```shell
El título del desafío sugiere que la bandera fue ocultada mediante esteganografía.

"St3g0" es una marca comúnmente empleada para la ocultación en el bit menos significativo en la codificación.

Al aplicar el comando "zsteg" a nuestro archivo, se revelan una serie de datos, y en ellos encontramos la bandera.
```
![[Pasted image 20231103030228.png]]
## Notas adicionales
Es necesario instalar zsteg con los siguientes comandos: "sudo gem install zsteg" y luego "sudo gem install zsteg".
## Referencias