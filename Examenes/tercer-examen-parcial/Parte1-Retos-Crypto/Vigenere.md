### Vigenere
## Objetivo
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".
## Solución 
```shell
  
Para abordar este problema, utilizaremos CyberChef. En primer lugar, debemos analizar el mensaje que dice lo siguiente:

rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}

Después de esto, debemos dirigirnos a CyberChef y seleccionar la opción de Descifrado Vigenere. Esta opción solicitará una clave, y en este caso, la clave es CYLAB. Con el mensaje ingresado en la sección de entrada, la salida será:

Resultado Final:

picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae8227q}
```
![[Pasted image 20231123071128.png]]
## Notas adicionales

## Referencias
[https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfZjg1NzI5ZTd9](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfZjg1NzI5ZTd9)