### GDB Test Drive
## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Solución 
```shell
Para superar este desafío, una vez que hayamos descargado el archivo, necesitamos asegurarnos de tener la librería gdb instalada.

Si ya está instalada, nos movemos al directorio donde se encuentra nuestro archivo y ejecutamos los comandos siguientes:
chmod +x gdbme
gdb gdbme
layout asm

Después de ejecutar los comandos mencionados anteriormente, se abrirá una nueva ventana que mostrará instrucciones del lenguaje ensamblador. Posteriormente, solo necesitamos seguir y aplicar dichas instrucciones.

break *(main+99)
run
jump *(main+104)

  
Cuando ejecutemos la última instrucción, obtendremos la bandera.

```

![[Pasted image 20231113033028.png]]
## Notas adicionales

## Referencias