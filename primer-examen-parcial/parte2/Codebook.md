## Codebook
## Objetivo
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)

Hints:
	On the webshell, use `ls` to see if both files are in the directory you are in
	The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución 
```shell
- DESCARGAR LOS ARCHIVOS "code.py" y "codebook.txt" usando wget.
israelga-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt
israelga-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_7d102d7a}
```
## Notas adicionales
Solo se requeria ejecutar code.py en el mismo directorio de codebook.txt
## Referencias