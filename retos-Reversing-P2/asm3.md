### asm3
## Objetivo
What does asm3(0xd2c26416,0xe6cf51f0,0xe54409d5) return? Submit the flag as a hexadecimal value (starting with '0x').
## Solución 
```shell
Datos de acceso:
0xd2c26416
0xe6cf51f0
0xe54409d5

ARCHIVO:

asm3:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	xor    eax,eax
	<+5>:	mov    ah,BYTE PTR [ebp+0x9]
	<+8>:	shl    ax,0x10
	<+12>:	sub    al,BYTE PTR [ebp+0xe]
	<+15>:	add    ah,BYTE PTR [ebp+0xf]
	<+18>:	xor    ax,WORD PTR [ebp+0x12]
	<+22>:	nop
	<+23>:	pop    ebp
	<+24>:	ret    

Usando un emulador dde Assembly x86 pegamos lo siguiente: 
Los "push" o datos de entrada se colocan en orden inverso; primero el ultimo que te de el reto y aspi susesivamente.

start:
	push 0xe54409d5
	push 0xe6cf51f0
	push 0xd2c26416
	call asm3
	
asm3:
	push   ebp
	mov    ebp,esp
	xor    eax,eax
	mov    ah,BYTE PTR [ebp+0x9]
	shl    ax,0x10
	sub    al,BYTE PTR [ebp+0xe]
	add    ah,BYTE PTR [ebp+0xf]
	xor    ax,WORD PTR [ebp+0x12]
	nop
	pop    ebp
	ret   


Dentro del emulador, despues de darle al menu derecho Windows y seleccionar registros, ejecutamos paso por paso, hasta terminar (como guia se termina en nop).
Nos importa lo que quede dentro del campo EAX, esa sera nuestra flag.
```
![[Pasted image 20231113025858.png]]

## Notas adicionales
Flag: 0x375
## Referencias
https://carlosrafaelgn.com.br/Asm86/
