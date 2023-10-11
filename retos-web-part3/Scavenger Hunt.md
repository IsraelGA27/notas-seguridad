## **Scavenger Hunt**

## Problema
There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:39698/). Can you find it?
## Solucion

Tenemos que buscar en los archivos fuentes para encontrar la bandera
![[Pasted image 20231011110532.png]]
![[Pasted image 20231011110706.png]]
En el archivo js nos muestra un mensaje, en el cual podemos deducir que la siguiente parte se va a encontrar en el archivo rorbots.txt. al ingresar ese archivo robots.txt aparece los siguiente
![[Pasted image 20231011110838.png]]
En algunas paginas por defecto guardan en un servidor apache algunas configuraciones para acceder a esas configuraciones ponemos el siguiente link .htaccess

![[Pasted image 20231011111107.png]]
Nos pide que busquemos en otro sitio [https://en.wikipedia.org/wiki/.DS_Store](https://en.wikipedia.org/wiki/.DS_Store). .DS_store guarda mucha mas informacion
![[Pasted image 20231011111215.png]]

picoCTF{t
h4ts_4_l0
t_0f_pl4c
3s_2_lO0k
_7a46d25d}

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}