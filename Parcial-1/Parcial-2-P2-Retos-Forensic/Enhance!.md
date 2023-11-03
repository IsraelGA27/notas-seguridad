### Enhance!
## Objetivo
Download this image file and find the flag.

- [Download image file](https://artifacts.picoctf.net/c/102/drawing.flag.svg)
## Solución 
```shell
Cuando tratamos de visualizar la imagen, notamos que no se muestra ningún contenido. Lo mismo ocurre al revisar los metadatos.

Por lo tanto, debemos analizar los strings. Si examinamos las líneas que incluyen la palabra clave **tspan** y contienen una palabra de la bandera, necesitaremos utilizar la herramienta "grep" para recopilar toda la información relevante.
```

![[Pasted image 20231103024724.png]]
## Notas adicionales
## Referencias