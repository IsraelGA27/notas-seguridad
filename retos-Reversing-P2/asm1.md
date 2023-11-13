### asm1
## Objetivo
What does asm1(0x2e0) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/f1c2358ff7d1e9386e41552c549cf2f6/test.S)
## Solución 
```shell
Vamos a analizar el código de ensamblador con la nueva entrada proporcionada `0x6fa`:

asm1:
    <+0>:  push   ebp
    <+1>:  mov    ebp,esp

    <+3>:  cmp    DWORD PTR [ebp+0x8],0x3a2
    <+10>: jg     0x512 <asm1+37>

    <+12>: cmp    DWORD PTR [ebp+0x8],0x358
    <+19>: jne    0x50a <asm1+29>
    <+21>: mov    eax,DWORD PTR [ebp+0x8]
    <+24>: add    eax,0x12
    <+27>: jmp    0x529 <asm1+60>

    <+29>: mov    eax,DWORD PTR [ebp+0x8]
    <+32>: sub    eax,0x12
    <+35>: jmp    0x529 <asm1+60>

    <+37>: cmp    DWORD PTR [ebp+0x8],0x6fa
    <+44>: jne    0x523 <asm1+54>
    <+46>: mov    eax,DWORD PTR [ebp+0x8]
    <+49>: sub    eax,0x12
    <+52>: jmp    0x529 <asm1+60>

    <+54>: mov    eax,DWORD PTR [ebp+0x8]
    <+57>: add    eax,0x12

    <+60>: pop    ebp
    <+61>: ret

Para `asm1(0x6fa)`, evaluemos las condiciones:

1. `0x6fa` es mayor que `0x3a2`, así que pasamos a la siguiente condición.
2. `0x6fa` no es igual a `0x358`, así que pasamos a la siguiente condición.
3. `0x6fa` es igual a `0x6fa`, por lo que ejecutamos la última condición.
4. Para la última condición, resta `0x12` al valor de entrada.

0x6fa - 0x12 = 0x6e8

Por lo tanto, si la entrada es `0x6fa`, el resultado correcto es `0x6e8`.
```
## Notas adicionales

## Referencias