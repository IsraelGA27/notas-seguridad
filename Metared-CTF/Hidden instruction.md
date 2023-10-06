## Hidden instruction
## Objetivo
We managed to intercept a suspicious file that wanted to be shared with cyber attackers, it is believed to contain hidden instructions, help us find out what message was intended to be shared.

Remember to use the flag format **flagMX{HIDDENINSTRUCTION}**
## Solución 
```shell
Usando Audacity pude disminuir la velocidad de reproducción del audio y aumentar su tono para escuchar la primera parte: EDFOKTLBPLVIMK la cual invertimos: KMIVLPBLTKOFDE

Despues la portada del audio usando tiene la cadena: STIESPI
```
![[Pasted image 20231004205805.png]]
![[Pasted image 20231004210357.png]]
Usando KMIVLPBLTKOFDE como texto y STIESPI como clave pude usar el cifrado Vigenere a través de un código de python.
![[Pasted image 20231004211943.png]]
![[Pasted image 20231004212327.png]]

Con eso nos da la flag: flagMX{STARTATTACKNOW}
## Notas adicionales
## Referencias