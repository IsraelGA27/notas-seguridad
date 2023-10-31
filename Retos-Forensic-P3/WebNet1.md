### WebNet1
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Solución 
Vamos a archivo para exportar los archivos.
![[Pasted image 20231030211042.png]]
Se envió una imagen, así que debemos guardarla.
![[Pasted image 20231030211134.png]]
Vamos a la terminal para extraer los string con el comando strings de la imagen para obtener la flag.
```shell
┌──(israel㉿Kali-IS)-[~/Descargas]
└─$ strings vulture.jpg | grep pico
 picoCTF{honey.roasted.peanuts}
                                                                          
┌──(israel㉿Kali-IS)-[~/Descargas]
└─$    
```
## Notas adicionales
## Referencias