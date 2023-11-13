### asm2
## Objetivo
What does asm2(0x4,0x21) return? Submit the flag as a hexadecimal value (starting with '0x')
## Solución 
```shell
Stack:
[ local4 ]  <--- ebp-0x10
[ local3 ]  <--- ebp-0xc
[ local2 ]  <--- ebp-0x8
[ local1 ]  <--- ebp-0x4    Esta es la estructura que se crea al seguir todos los pasos
[   ebp   ]
[   ret   ]  <--- ebp+0x4
[   arg1  ]  <--- ebp+0x8
[   arg2  ]  <--- ebp+0xc
```
```python
# Los argumentos que recibe asm2
def asm2(arg1, arg2):
    # <+0>:  push   ebp
    # <+1>:  mov    ebp,esp
    # <+3>:  sub    esp,0x10

    # <+6>:  mov    eax,DWORD PTR [ebp+0xc]
    eax = arg2

    # <+9>:  mov    DWORD PTR [ebp-0x4],eax
    local1 = eax

    # <+12>: mov    eax,DWORD PTR [ebp+0x8]
    eax = arg1

    # <+15>: mov    DWORD PTR [ebp-0x8],eax
    local2 = eax

    # <+18>: jmp    0x509 <asm2+28>
    # <+20>: add    DWORD PTR [ebp-0x4],0x1
    # <+24>: add    DWORD PTR [ebp-0x8], 0x74
    # <+28>: cmp    DWORD PTR [ebp-0x8], 0xfb46
    # <+35>: jle    0x501 <asm2+20>
    while(local2 <= 0xfb46):
        # Esto trunca el resultado a 32 bits. 
        local1 = (local1 + 1) & 0xffffffff
        # Esto trunca el resultado a 32 bits. 
        local2 = (local2 + 0x74)  & 0xffffffff

    # <+37>: mov    eax,DWORD PTR [ebp-0x4]
    # <+40>: leave
    # <+41>: ret
    return hex(local1)

print(asm2(0x4, 0x21))  # Aquí van los valores que nos da el reto

```
## Notas adicionales

## Referencias

