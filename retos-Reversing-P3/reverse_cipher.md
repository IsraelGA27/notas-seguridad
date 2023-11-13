### reverse_cipher
## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.
## Solución 
```shell
Antes de empezar debemos verificar que tengamos la herramienta `ghidra` instalada en nuestro sistema Linux.
sudo apt install ghidra 

Con esta herramienta, podemos examinar la lógica utilizada para cifrar la bandera. Al analizar el documento "rev_this", descubriremos lo siguiente.

Examinando el algoritmo de cifrado, es posible desarrollar un script en Python para descifrar la bandera. El código resultante se presenta a continuación
```
```python
cf = open ('rev_this','r').read()
fl = ''

for i in range(8, len(cf) -1):
	if i & 1 == 0:
		fl += chr( ord(cf[i]) - 5 )
	else:
		fl += chr( ord(cf[i]) + 2 )

print(f"picoCTF{{{flag}}}")
```
![[Pasted image 20231113035040.png]]
## Notas adicionales

## Referencias
