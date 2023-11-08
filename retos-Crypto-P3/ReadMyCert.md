### ReadMyCert
## Objetivo
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/422/readmycert.csr).
## Solución 
```shell
Comando: openssl req -in readmycert.csr -noout -text

La flag saldrá dentro del campo Subject: CN.
```
![[Pasted image 20231108012459.png]]
## Notas adicionales
## Referencias
[https://www.sslshopper.com/csr-decoder.html](https://www.sslshopper.com/csr-decoder.html)
[https://www.openssl.org/docs/manmaster/man1/openssl-req.html](https://www.openssl.org/docs/manmaster/man1/openssl-req.html)