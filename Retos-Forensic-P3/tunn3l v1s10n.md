### tunn3l v1s10n
## Objetivo
We found this [file](https://mercury.picoctf.net/static/da18eed3d15fd04f7b076bdcecf15b27/tunn3l_v1s10n). Recover the flag.
## Solución 
Revisamos el tipo de archivo dándonos data, tenemos que convertirlo en imagen, para esto usaremos el editor hexadecimal "hexeditor".
Abriéndolo pasamos 0xE usando ctrl + t.

![[Pasted image 20231030210153.png]]
![[Pasted image 20231030210555.png]]
Y escribimos lo siguiente y abrimos la imagen. Esta aparece recortada, entonces la ampliamos el alto de la imagen volviendo al editor, con el espacio 0x12 y lo modificamos.
![[Pasted image 20231030210628.png]]

![[Pasted image 20231030210648.png]]
![[Pasted image 20231030210819.png]]
 Y obtenemos la flag.
 ![[Pasted image 20231030210842.png]]
## Notas adicionales
## Referencias