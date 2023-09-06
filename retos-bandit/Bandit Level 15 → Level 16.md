# Bandit Level 15 → Level 16
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Datos de acceso al nivel
```
ssh bandit15@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Solución 
```
bandit15@bandit:~$ pwd
/home/bandit15
bandit15@bandit:~$ ls
bandit15@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r-----  1 bandit15 bandit15   33 Apr 23 18:04 .bandit14.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  5 14:21:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  5 14:21:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  5 14:20:56 2023 GMT; NotAfter: Sep  5 14:21:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIERT5t9zANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTA1MTQyMDU2WhcNMjMwOTA1MTQyMTU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCm
wBiPjdh1RI2h6uD0NBu9weZgCFgUwOM5PTlJzrrbDIG6MojStI6UWFDOGJAGYk/O
3vOKI4XC1r51gsOG+JSQye+9XqlNKVidFm8muvoOQhtCb3vquFm1kn4B5ZlVFPE+
kwN9TB+Vv9vfwXI3HG7o5KBRBZRPKV1KNOU+x3jhjphuXbLOi0PeNHWAyEBHfNEX
Zrz+Zvun+kgq8CmGGp9oMYRfwjmvPaZYQtTH/JUmt7vbsXalAb6oaCHx36GeuEJH
lAoPkI++eVSLJQO7tdtMeNpYKttX1jIjVvMqAKf7Nhx91m7A1mBGjUw8FDjZjhjn
ynORJxJii0nCah3xomyHAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAx
ECelAuW6irw6S0/rR2vxrL9Oeej7SWiQ1CizTLew+HZRzRQmTwGqmYnSQnMUhCRT
u5vFwP6tnDrUXlSrazBnDve87BMzdECWhauErj9Pt40gLDuSgvLkZWl6P+f8Frb8
FkDUXuqxiq1vZxOcY0gSQpwvLeS06RMi546KNmDt4+Qfvqt4oXRL+882bqgoOqHQ
P/VsqO52CXoAe5rLuhyC/YVnWxIQnjE5EUYkXCd0Zdm7JOzuKbid7FGinAnpzfUz
vaG4FaUl1ITlxUE9xAWiDIDBYZuXUbj8CyipZm+v0ksNPqXYkh/PvK24fyaAeAUL
Yrmp3Qa25oeRjlPTmVTD
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9597873198920F73E91F99D0B13DBF68CF1C255BCA684BEB33179FA5656A9CCF
    Session-ID-ctx:
    Resumption PSK: FBC31534754DBB028AF917B1C435AE705FE3D53EEC683F23F88539A1FE2DE831CD8B62045D2360D571F2A95C83AF4FDC
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 48 a5 32 54 0e cb 4c-36 de e2 24 47 c1 4f 66   .H.2T..L6..$G.Of
    0010 - c3 09 6f 05 85 ac 27 53-43 4e ca 06 36 07 cb 0a   ..o...'SCN..6...
    0020 - e1 2d 3c ea aa 33 fb 44-81 88 00 41 7f 9c ff 3c   .-<..3.D...A...<
    0030 - 44 45 35 8a e4 1d 94 b1-e9 5f c6 4f 9c ba 29 49   DE5......_.O..)I
    0040 - 78 f9 51 bd 29 b1 bf ec-34 5c e9 a9 67 8e 55 d8   x.Q.)...4\..g.U.
    0050 - b4 49 e6 a0 63 e1 87 b6-e2 df 64 38 13 61 0f 9d   .I..c.....d8.a..
    0060 - 6a 95 6b 59 5c 89 e7 40-09 ff 1a 55 73 51 43 b6   j.kY\..@...UsQC.
    0070 - 16 7e 8a 81 78 2a 64 95-59 b5 fe 11 21 bf a1 33   .~..x*d.Y...!..3
    0080 - bb 50 d6 30 68 fb e6 39-dd 9a ab db ab a8 ac 3f   .P.0h..9.......?
    0090 - 08 84 c9 c4 8b c9 1a 28-07 c2 38 77 b4 4f 11 79   .......(..8w.O.y
    00a0 - b1 3d 55 c2 f0 a4 42 75-0d be fc 11 7b 6a 1c b4   .=U...Bu....{j..
    00b0 - f7 9d 37 16 3d 06 f6 20-f1 7d 3a 75 36 0f 69 af   ..7.=.. .}:u6.i.
    00c0 - e6 71 68 80 54 47 63 40-07 99 0c 4d 5c 93 11 f2   .qh.TGc@...M\...

    Start Time: 1694017963
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: F1595447869A5602E0710EA231EA2E27824A598D239D0FACBA84704BE0B2FD8F
    Session-ID-ctx:
    Resumption PSK: B89474464A9EC1BD16C46D206DBDC89297B617B8C76F88547FDA87379BC8AD0DDB6CC6E7399A6A0B759600D1D5C8D743
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 48 a5 32 54 0e cb 4c-36 de e2 24 47 c1 4f 66   .H.2T..L6..$G.Of
    0010 - 6b 40 64 b7 28 9d 6c e2-04 d0 54 15 9d c5 93 d5   k@d.(.l...T.....
    0020 - 27 52 9b 90 5b 7e 0a 60-41 6f bf 09 f2 1a 51 e0   'R..[~.`Ao....Q.
    0030 - 18 3e 7c db b6 6c 17 b4-03 e5 dc 48 c9 0d 19 f3   .>|..l.....H....
    0040 - 28 53 dd cb 31 e9 b8 06-b9 d3 25 56 8e 8f 6f 6f   (S..1.....%V..oo
    0050 - 4b 8a ce 0a 65 0a c4 ed-a9 73 da f9 4b 18 a8 ca   K...e....s..K...
    0060 - 9f 7b fe 10 5c dc 3a ba-36 a4 47 77 f0 7d f2 4b   .{..\.:.6.Gw.}.K
    0070 - 20 21 a2 c3 77 6b 80 70-c3 54 f3 65 eb b9 0f 52    !..wk.p.T.e...R
    0080 - 5b ac 83 6b ed 9f de 4b-1d 4e e8 cb b7 b6 05 1f   [..k...K.N......
    0090 - c1 6e 98 ad ce b9 fa 80-2b 3a 84 81 7d 0a 69 e6   .n......+:..}.i.
    00a0 - f8 f8 18 6c ab 2e 55 16-13 26 f2 f9 b9 b9 de 34   ...l..U..&.....4
    00b0 - 96 18 4c b3 cf eb b4 ab-67 17 45 4f 81 d7 bf f0   ..L.....g.EO....
    00c0 - fb b5 9d 9c 68 d6 a1 a2-dc 6e d8 30 3e 82 37 c0   ....h....n.0>.7.

    Start Time: 1694017963
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```
## Notas adicionales
Iniciar una conexión SSL/TLS a un servidor en el host local (localhost) en el puerto 30001 utilizando la utilidad OpenSSL.

- `openssl`: Este es el comando principal para trabajar con la biblioteca OpenSSL, que proporciona funciones criptográficas y de seguridad.
    
- `s_client`: Esta parte del comando especifica que se debe iniciar un cliente SSL/TLS. Esto significa que el comando actuará como un cliente que intentará establecer una conexión segura con un servidor remoto.
    
- `-connect localhost:30001`: Esta opción indica a OpenSSL la dirección y el puerto al que debe conectarse. En este caso, se está conectando a "localhost" en el puerto "30001".
El comando `openssl s_client -connect localhost:30001` se utiliza para establecer una conexión segura con un servidor que está escuchando en el puerto 30001 en el host local. Esta conexión se realizará utilizando el protocolo SSL/TLS y se utiliza comúnmente para verificar la configuración SSL/TLS de un servidor y realizar pruebas de conectividad segura.
## Referencias
- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)