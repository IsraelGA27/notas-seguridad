### miniRSA
## Objetivo
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.
## Solución 
Importamos:
![[Pasted image 20231103051807.png]]
Ajustamos la precisión a 2048
![[Pasted image 20231103051952.png]]


![[Pasted image 20231103051352.png]]
```shell
┌──(israel㉿Kali-IS)-[~]  
└─$ python3  
Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux  
Type "help", "copyright", "credits" or "license" for more information.  
>>> from gmpy2 import *  
>>> from Crypto.Util.number import long_to_bytes  
>>>  
>>> gmpy2.get_context().precision=2048  
>>>  
>>> e = 3  
>>> c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933  
>>>  
>>> root, exact = iroot(c, e)  
>>> root  
mpz(13016382529449106065894479374027604750406953699090365388203708028670029596145277)  
>>>  
>>> print( long_to_bytes(root) )  
b'picoCTF{n33d_a_lArg3r_e_ccaa7776}'  
>>>
```
## Notas adicionales
Descargar gmpy2
![[Pasted image 20231103051452.png]]
Tener instaldado pycryptodome.
![[Pasted image 20231103051612.png]]
## Referencias