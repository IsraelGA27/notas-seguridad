## c0rrupt
## Objetivo
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
## Solución 
Primero verificamos el tipo de archivo, usando el comando file, con lo cual nos da que es tipo "data".
![[Pasted image 20231025101612.png]]
Tenemos que modificar con el editor hexadecimal ya que el archivo esta corrupto.
![[Pasted image 20231025101433.png]]
![[Pasted image 20231025101451.png]]
Cuando queremos abrirlo, nos muestra que no es posible, que aun se encuentra corrupto, por lo que verificamos la imagen con el pngcheck.
![[Pasted image 20231025101232.png]]
Se puede observar que hay un error y lo corregimos.
![[Pasted image 20231025101905.png]]
![[Pasted image 20231025101913.png]]
## Notas adicionales
CTF: ![[Pasted image 20231025101807.png]]
## Referencias