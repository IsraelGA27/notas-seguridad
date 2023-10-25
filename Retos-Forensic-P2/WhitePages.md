### WhitePages
## Objetivo

## Solución 
```python
# coding=utf8

  

text = '                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                '

firstType = ' '

secondType = ' '

binaryString = ''

  

for char in text:  # Foreach char

    if char == firstType:  # Check if it is the first type

        binaryString += '0'  # Mark it as 0

    else:

        binaryString += '1'  # Mark it as 1

  

print(binaryString)  # Print result
```
![[Pasted image 20231025105750.png]]
## Notas adicionales
## Referencias
https://www.rapidtables.com/convert/number/binary-to-ascii.html
