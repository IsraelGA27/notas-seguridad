## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
## Solución 
Se descargan los archivos y abrimos el programa wireshark.
Abrimos preferencias y buscamos el puerto TLS agregamos la llave que nos dieron y a partir de eso podemos buscar la bandera.
![[Pasted image 20231025111438.png]]
Buscamos "pico" en los detalles del paquete.
![[Pasted image 20231025111502.png]]
picoCTF{nongshim.shrimp.crackers}
## Notas adicionales
## Referencias