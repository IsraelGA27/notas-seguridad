### Roboto Sans
## Objetivo
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:59901/) out.
## Solución 
```shell
Solamente por el nombre de robots del reto podemos deducir que debemos buscar algo en el archivo robots.txt. Al momento de abrirlo nos da lineas posiblemente incripatdas la segunda anMvbXlmaWxlLnR4dA especificamente usando base64 nps da js/myfile.txt, al colocar la ultima como dirección nos da la flag correspondiente del reto.
```

![[Pasted image 20231103021650.png]]

![[Pasted image 20231103021741.png]]
![[Pasted image 20231103021833.png]]
## Notas adicionales
Un archivo robots.txt indica a los rastreadores de motores de búsqueda a qué URL puede acceder el rastreador en su sitio.
## Referencias
https://www.base64decode.org