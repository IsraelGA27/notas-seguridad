## JaWT Scratchpad
## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090
## Solución 
```shell
picoCTF{jawt_was_just_what_you_thought_f859ab2f}
```
Usando Cookie editor obtenemos las cookies del sitio para modificarla, exactamente la jwt.
La copeamos y llevamos a jwt.io para descubrir la flag, usando como usuario admin y ilovepico.
![[Pasted image 20231010144617.png]]
![[Pasted image 20231010144741.png]]
## Notas adicionales
## Referencias
https://jwt.io/