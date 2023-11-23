### PW Crack 3
## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución 
```shell
Contenido .py:
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()

Contenido .enc:
B[ZZqf^?N_^F^L]mTU^D\U^H[Um^OS^K
X^A^KTD

Contenido .bin:
^V^Bm` ^{TA^K45 ^C  &

La idea es hacer un hash de cada una de las posibles contraseñas para compararlas con el hash correcto. Lo hacemos agregando un bucle for simple antes de la verificación.


MOD:
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"] #Modificado

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    #user_pw = input("Please enter correct password for flag: ")
    #user_pw_hash = hash_pw(user_pw)
    
    #if( user_pw_hash == correct_pw_hash ):
        #print("Welcome back... your flag, user:")
        #decryption = str_xor(flag_enc.decode(), user_pw)
        #print(decryption)
        #return
    #print("That password is incorrect")
    #hash each possible pw
    for i in pos_pw_list:
        user_pw_hash = hash_pw(i)

        if( user_pw_hash == correct_pw_hash ):
            print(f"The correct pw is {i}") #prints the pw that worked
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), i) #update user_pw to i
            print(decryption)
            return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
#pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

israelga-picoctf@webshell:~$ ls
README.txt  level3.flag.txt.enc  level3.hash.bin  level3.py
israelga-picoctf@webshell:~$ nano level3.py
israelga-picoctf@webshell:~$ nano level3.flag.txt.enc 
israelga-picoctf@webshell:~$ nano level3.hash.bin
israelga-picoctf@webshell:~$ nano level3.py
israelga-picoctf@webshell:~$ python level3.py
The correct pw is 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
israelga-picoctf@webshell:~$ 
```
## Notas adicionales
## Referencias