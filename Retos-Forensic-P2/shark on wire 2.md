### shark on wire 2
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución 
Abro el archivo pcap con Wireshark, empiezo a filtrar los protocolos udp y tcp, miro las transmisiones y busco el contenido de los paquetes.
Pero no salió nada, así que eché un vistazo al foro de Piazza para obtener algunas pistas, y la principal conclusión de las publicaciones fue que la bandera no está en el cuerpo, y traté de encontrar un mensaje de que el cuerpo parecía sospechoso y miré. los encabezados. Así que de nuevo filtrando y filtrando de nuevo, hasta que encontré esto:
![[Pasted image 20231025110031.png]]
Filtro:
![[Pasted image 20231025110232.png]]
112 105 99 111 67 84 70 123 112 49 76 76 102 51 114 51 100 95 100 97 116 97 95 118 49 97 95 115 116 51 103 48 125
![[Pasted image 20231025110350.png]]
## Notas adicionales
## Referencias