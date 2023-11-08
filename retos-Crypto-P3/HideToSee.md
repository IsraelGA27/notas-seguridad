### HideToSee
## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg).
## Solución 
```shell
atbash.jpg.
Extraiga datos ocultos con steghide (sin contraseña):

El nombre del archivo atbash.jpg es una pista del algoritmo de codificación que se utiliza para la bandera.
```
![[Pasted image 20231108010847.png]]
Código para descifrar la flag.
```python
#!/usr/bin/python3

# Mapping between English alphabet & Atbash cipher

# Create list of alphabetical letters
alphabet = list("abcdefghijklmnopqrstuvwxyz")
    
# Atbash's single substitution key is having all the letters be reversed. So create reverse alphabet
atbash = alphabet[::-1]

# Construct a dictionary matching English letters to Atbash letters.
map = dict(zip(alphabet, atbash))

#Take input from user.
user_input = list(input("What is the encoded message? \n >>>"))
    
#placeholder for decoded message
decoded = []

for i in user_input:
    # Exclude numbers, curly brackets and hyphens, leave only the letters
    if i.isnumeric() == False and i != "{" and i != "}" and i != "_":
        # Convert to lower case for consistency.
        i = i.lower()
        # Add the matching Atbash letter to decoded
        decoded.append(map[i])
    else:
        # Add digits and curly brackets normally
        decoded.append(i)
    
    # convert decoded list back into string
    message = "".join(decoded)

print(f"Your decoded message is: {message}")
```
![[Pasted image 20231108011558.png]]
## Notas adicionales
## Referencias