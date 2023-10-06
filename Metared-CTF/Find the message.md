## Find the message
## Objetivo
You have the file 2023Metared.jpg Can you find the flag?
https://ctfd.anuies.mx/files/bc8e90261d26030d76237cba0791d30b/2023Metared.jpg?token=eyJ1c2VyX2lkIjoyMzIsInRlYW1faWQiOjk4LCJmaWxlX2lkIjoxNX0.ZR3vMA.RSk4uGRDDfAmPOpX-ggt8rqtJ5g
## Solución 
```shell
usando exiftool + {nombre del archivo} pude ver los meta datos de este, donde dentro de la descripción de la imagen se encontraban 2 coordenadas, las cuales me llevaban a la Universidad Veracruzana.
```
![[Pasted image 20231004170359.png]]

Con binwalk pude ver que el archivo .jpg contenía dentro de el un archivo PDF
![[Pasted image 20231004170550.png]]

Después con foremost extraje el pd dentro de una carpeta llamada outout
![[Pasted image 20231004170756.png]]

Usando "UniversidadVeracruzana" como contraseña para desbloquear el PDF extraido. Ah primera vista se veía como un archivo en blanco pero tenia una tipografía seleccionable, con un convertidor obtuve la FLAG.
![[Pasted image 20231004170925.png]]
![[Pasted image 20231004171510.png]]
## Notas adicionales
## Referencias