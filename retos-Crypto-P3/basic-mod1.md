### basic-mod1
## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solución 
```shell
La descripción muestra el cifrado con las siguientes reglas:
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140 

Vamos a leer message.txt y calcula el mod37.
```
```python
def decode(number):

    r = number % 37

    return r

  

def main():

    f = open("message.txt", "r", encoding="UTF-8")

    lst = f.read().split()

    # print(lst[0])

  

    dec_lst = []

  

    for i in range(len(lst)):

        dec_lst.append(decode(int(lst[i])))

  

    print(dec_lst)

  

if __name__ == '__main__':

    main()
```
![[Pasted image 20231108005013.png]]
Con eso solo calculamos con las reglas anteriores:
```ýthon
import string

alfabeto = string.ascii_lowercase

alfabeto += "0123456789_"

  

flag_enc = [17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 33, 35, 2, 27, 34, 5, 1, 29]

flag = ""

for c in flag_enc:

    pos = c % 37

    flag += alfabeto[pos]

  

print(flag)
```
![[Pasted image 20231108005431.png]]
## Notas adicionales
Flag: 

[17, 26, 20, 13, 3, 36, 13, 36, 17, 26, 20, 13, 3, 36, 33, 35, 2, 27, 34, 5, 1, 29]
r0und_n_r0und_79c18fb3
picoCTF{r0und_n_r0und_79c18fb3}
## Referencias