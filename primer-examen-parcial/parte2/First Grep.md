## First Grep
## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.
## Solución 
```shell
israelga-picoctf@webshell:~$ ls
README.txt  file
israelga-picoctf@webshell:~$ file file
file: ASCII text, with very long lines (4200)
israelga-picoctf@webshell:~$ grep -e 'pico' file
picoCTF{grep_is_good_to_find_things_dba08a45}
israelga-picoctf@webshell:~$ 
```
## Notas adicionales
## Referencias
https://ryanstutorials.net/linuxtutorial/grep.php