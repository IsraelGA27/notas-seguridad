## Nice netcat...
## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 43239`, but it doesn't speak English...
Hints:
	You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
	You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solución 
```shell
israelga-picoctf@webshell:~$ nc mercury.picoctf.net 43239
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
55 
99 
48 
56 
50 
49 
102 
53 
125 
10

Con la página de CyberChef usando la formula de FROM DECIMAL, coloque los numeros que me dio nc y me devolvio la flag.
picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}
```
## Notas adicionales
Con la página de CyberChef usando la formula de FROM DECIMAL, coloque los numeros que me dio nc y me devolvio la flag.
## Referencias
https://gchq.github.io/CyberChef/ (Usando FROM DECIMAL)
https://onlinetools.com/ascii/convert-decimal-to-ascii
