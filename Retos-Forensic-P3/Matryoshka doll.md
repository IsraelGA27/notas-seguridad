### Matryoshka doll

## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg)
## Solución 
```shell
Contiene imagenes dentro de otra imagen, lo que tenemos que realizar es extraer esas imagen de la imagen con el comando binwalk — extrackt
```

![[Pasted image 20231030205540.png]]
Mismo procedimiento hasta 4 veces y obtener el archivo con la flag.
![[Pasted image 20231030205634.png]]

## Notas adicionales
## Referencias