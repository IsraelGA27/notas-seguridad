### SRA
## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.
## Solución 
```shell
  
El propósito del archivo chal.py es comprender la lógica utilizada dentro del servidor. Al ejecutarlo, debería generar valores aleatorios, como los siguientes:

pythonCopy code

anger = 50720326544381967175340270599657266842766060092472813893678828531389866607968  
envy = 2177544366013393820852938514621636235843661021841770438601598186754042347233  
vainglory?

Al analizar el código, observamos que contiene la mayoría de los elementos de RSA, pero solo podemos interactuar con tres de ellos. Dos de estos son "anger", que representa el texto cifrado, y "envy", que corresponde a "d". Por otro lado, el tercer valor que podemos determinar es el de "sloth", ya que es el exponente de la llave pública.

Cada vez que se ejecuta el código, todos los valores, excepto la llave pública "sloth", cambian. Dado que no podemos modificar el código fuente y eventualmente se ejecutará en un servidor que solo permite la entrada de datos, la mejor opción es crear un script que tome en cuenta los cambios para las variables "anger" y "envy".

El script propuesto sería el siguiente: 
```
```python
from Crypto.Util.number import isPrime, long_to_bytes
from string import ascii_letters, digits
from itertools import combinations
from sympy import divisors
from math import log2

anger = int(input("anger = "))
envy = int(input("envy = "))
sloth = 65537

ds = divisors(envy * sloth - 1)
primes = [x + 1 for x in ds if isPrime(x + 1)]
correct_size_primes = [x for x in primes if log2(x) // 1 == 127]

valid_plaintexts = []
charset = ascii_letters + digits
for p, q in combinations(correct_size_primes, 2):
    try:
        s = long_to_bytes(pow(anger, envy, p * q)).decode("ascii")
        if all([c in charset for c in s]):
            valid_plaintexts.append(s)
    except Exception:
        continue

print(valid_plaintexts)
```
```shell
Teniendo nuestro script listo ahora debemos acceder al servidor


┌──(israel㉿Kali-IS)-[~/Descargas]  
└─$ nc [saturn.picoctf.net](http://saturn.picoctf.net/) 65032  
anger = 50720326544381967175340270599657266842766060092472813893678828531389866607968  
envy = 2177544366013393820852938514621636235843661021841770438601598186754042347233  
vainglory?



con los valores que nos dan ahora tenemos que ejecutar nuestro script en Python el cual nos pedirá los valores para `anger` y `envy`

```python
python3 exe.py
anger = 50720326544381967175340270599657266842766060092472813893678828531389866607968
envy = 2177544366013393820852938514621636235843661021841770438601598186754042347233 
['ysTEbKQsephdnUvG']
```

Después de procesar los datos nos dará la respuesta misma que tenemos que ingresar en el servidor

```shell
┌──(israel㉿Kali-IS)-[~/Descargas]  
└─$ nc [saturn.picoctf.net](http://saturn.picoctf.net/) 65032  
anger = 50720326544381967175340270599657266842766060092472813893678828531389866607968  
envy = 2177544366013393820852938514621636235843661021841770438601598186754042347233  
vainglory?  
> ysTEbKQsephdnUvG  
ysTEbKQsephdnUvG  
Conquered!  
picoCTF{7h053_51n5_4r3_n0_m0r3_3858bd66}

```

Al validarse los resultados nos dará la contraseña
picoCTF{7h053_51n5_4r3_n0_m0r3_3858bd66}
## Notas adicionales

## Referencias