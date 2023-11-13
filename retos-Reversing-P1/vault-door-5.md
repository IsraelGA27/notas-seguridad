### vault-door-5
## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)
## Solución 
```shell
  
Vi el código fuente y vi que verificaban su entrada después de codificarla en URL y luego codificarla en base64. La comparación es con esta salida.

Use un código en python para pasar todo directamente

import base64

  

encoded = 'JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTMwJTYyJTM5JTM1JTM3JTYzJTM0JTY2'

data = base64.b64decode(encoded).decode('utf-8')

print(data)

data = data.replace('%', ' 0x')

print(data)

  

ch = data.split(" ")

print(ch)

  

print('picoCTF{', end = '')

for c in ch:

    if(c != ''):

        print(chr(int(c, 16)), end = '')

  

print('}\n', end = '')

SALIDA:

%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%30%62%39%35%37%63%34%66
 0x63 0x30 0x6e 0x76 0x33 0x72 0x74 0x31 0x6e 0x67 0x5f 0x66 0x72 0x30 0x6d 0x5f 0x62 0x61 0x35 0x65 0x5f 0x36 0x34 0x5f 0x30 0x62 0x39 0x35 0x37 0x63 0x34 0x66
['', '0x63', '0x30', '0x6e', '0x76', '0x33', '0x72', '0x74', '0x31', '0x6e', '0x67', '0x5f', '0x66', '0x72', '0x30', '0x6d', '0x5f', '0x62', '0x61', '0x35', '0x65', '0x5f', '0x36', '0x34', '0x5f', '0x30', '0x62', '0x39', '0x35', '0x37', '0x63', '0x34', '0x66']
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}
```
## Notas adicionales
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}
## Referencias