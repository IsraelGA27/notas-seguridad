# Bandit Level 12 → Level 13
## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Datos de acceso al nivel
```
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
## Solución 
```bash
bandit12@bandit:/tmp$ mktemp -d
/tmp/tmp.eCyZitnDCP
bandit12@bandit:/tmp$ cd /tmp/tmp.eCyZitnDCP
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ cp ~/data.txt .
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
data.txt
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv data.txt hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ cat hexdump_data | head
00000000: 1f8b 0808 2773 4564 0203 6461 7461 322e  ....'sEd..data2.
00000010: 6269 6e00 0145 02ba fd42 5a68 3931 4159  bin..E...BZh91AY
00000020: 2653 597b 4f96 5f00 0018 ffff fd6f e7ed  &SY{O._......o..
00000030: bff7 bef7 9fdb d7ca ffbf edff 8ded dfd7  ................
00000040: bfe7 bbff bfdb fbff ffbf ff9f b001 3b56  ..............;V
00000050: 0400 0068 0064 3400 d341 a000 0680 0699  ...h.d4..A......
00000060: 0000 69a0 0000 1a00 1a0d 0034 0034 d3d4  ..i........4.4..
00000070: d1a3 d464 6834 6403 d469 b422 0d00 3400  ...dh4d..i."..4.
00000080: 1a68 068d 3403 4d06 8d00 0c80 00f5 0003  .h..4.M.........
00000090: 4031 3119 00d0 1a68 1a34 c86d 4640 00d0  @11....h.4.mF@..
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd -r hexdump_data compressed_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ cat compressed_data | head
@4Aڀh4C@hd2@hF4XdBGaB~6VAGf͌>G`wBx)B׭xk|IFDs>R4"^d!P^g!)O^1IF       7kFx,2<AVPIdJ-Se'yň`_1��Ft#^haX"l=]fwDZo,AB
4@weRI7}8v9H;uH%}$iKL12v)|Rib AN]BA>Y|.Ebandit12@bandit:/tmp/tmp.eCyZitnDCP$ cat hexdump_data
00000000: 1f8b 0808 2773 4564 0203 6461 7461 322e  ....'sEd..data2.
00000010: 6269 6e00 0145 02ba fd42 5a68 3931 4159  bin..E...BZh91AY
00000020: 2653 597b 4f96 5f00 0018 ffff fd6f e7ed  &SY{O._......o..
00000030: bff7 bef7 9fdb d7ca ffbf edff 8ded dfd7  ................
00000040: bfe7 bbff bfdb fbff ffbf ff9f b001 3b56  ..............;V
00000050: 0400 0068 0064 3400 d341 a000 0680 0699  ...h.d4..A......
00000060: 0000 69a0 0000 1a00 1a0d 0034 0034 d3d4  ..i........4.4..
00000070: d1a3 d464 6834 6403 d469 b422 0d00 3400  ...dh4d..i."..4.
00000080: 1a68 068d 3403 4d06 8d00 0c80 00f5 0003  .h..4.M.........
00000090: 4031 3119 00d0 1a68 1a34 c86d 4640 00d0  @11....h.4.mF@..
000000a0: 0007 a80d 000d 00e9 a340 d034 0341 a000  .........@.4.A..
000000b0: 0699 07a9 881e a0d0 da80 6834 0c43 4068  ..........h4.C@h
000000c0: 6432 0340 0c80 6800 0346 8006 8000 d034  d2.@..h..F.....4
000000d0: 0001 f0e1 810e 1958 b7a4 92c7 640e 421a  .......X....d.B.
000000e0: a147 6142 a67e 3603 a756 3ba9 1b08 e034  .GaB.~6..V;....4
000000f0: 41fd 1247 661d b380 00b7 cd8c b23e b6b2  A..Gf........>..
00000100: 1947 e803 0be5 6077 a542 e9ea 7810 29f0  .G....`w.B..x.).
00000110: 429d e1d7 ad8b 0b78 056b e37c 06df 4917  B......x.k.|..I.
00000120: 9b46 f69d 4473 80b4 edc2 ee10 04e3 3e52  .F..Ds........>R
00000130: dd34 2244 08cb 5e64 9314 9521 505e e767  .4"D..^d...!P^.g
00000140: 9021 d029 85e7 9ce2 d1ce d44f 5ec5 f6d6  .!.).......O^...
00000150: d918 de31 f1f5 d149 4695 0937 d06b f046  ...1...IF..7.k.F
00000160: 789d 1bd0 ca69 11eb 2c9a 3290 3d9e 0511  x....i..,.2.=...
00000170: 6cad 205b edc8 c4b5 4691 379a 5978 58c3  l. [....F.7.YxX.
00000180: 4846 a4a0 3ba5 a89a a794 1f93 c588 8160  HF..;..........`
00000190: 016e 2504 2c74 643b 5046 4154 751c 33b1  .n%.,td;PFATu.3.
000001a0: c3e5 53d8 a959 5fdc 6c12 f2bd 02f3 2d83  ..S..Y_.l.....-.
000001b0: b965 3188 0d3c b097 4156 e950 9d49 64f6  .e1..<..AV.P.Id.
000001c0: da4a 2db5 a4ea 5365 27c0 1e79 8109 5f31  .J-...Se'..y.._1
000001d0: c184 46c9 74a5 f923 5ea1 6861 f058 226c  ..F.t..#^.ha.X"l
000001e0: 3df6 5d10 d11f d966 77c9 e488 448c 5a6f  =.]....fw...D.Zo
000001f0: 2c10 410b 4280 140a 0818 8afa 0cfa 8bf7  ,.A.B...........
00000200: ad34 3308 4077 6552 9849 378e 7d85 1fd8  .43.@weR.I7.}...
00000210: f287 1238 7639 11e2 f1e6 483b 7548 25e2  ...8v9....H;uH%.
00000220: 7de4 24ff 1a69 0b85 4b4c ebd0 1231 a512  }.$..i..KL...1..
00000230: f9fb 109c e7ea d932 98fd eb76 f4f8 fa29  .......2...v...)
00000240: 967c e152 9c69 c607 6207 eaef 2095 9441  .|.R.i..b... ..A
00000250: a64e 9ffc 5dc9 14e1 4241 ed3e 597c 9f2e  .N..]...BA.>Y|..
00000260: f0c8 4502 0000                           ..E...
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv compressed_data compressed_fata.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_fata.gz  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ gzip -d compressed_fata.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_fata  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd compresed_fata
xxd: compresed_fata: No such file or directory
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_fata  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd compressed_fata
00000000: 425a 6839 3141 5926 5359 7b4f 965f 0000  BZh91AY&SY{O._..
00000010: 18ff fffd 6fe7 edbf f7be f79f dbd7 caff  ....o...........
00000020: bfed ff8d eddf d7bf e7bb ffbf dbfb ffff  ................
00000030: bfff 9fb0 013b 5604 0000 6800 6434 00d3  .....;V...h.d4..
00000040: 41a0 0006 8006 9900 0069 a000 001a 001a  A........i......
00000050: 0d00 3400 34d3 d4d1 a3d4 6468 3464 03d4  ..4.4.....dh4d..
00000060: 69b4 220d 0034 001a 6806 8d34 034d 068d  i."..4..h..4.M..
00000070: 000c 8000 f500 0340 3131 1900 d01a 681a  .......@11....h.
00000080: 34c8 6d46 4000 d000 07a8 0d00 0d00 e9a3  4.mF@...........
00000090: 40d0 3403 41a0 0006 9907 a988 1ea0 d0da  @.4.A...........
000000a0: 8068 340c 4340 6864 3203 400c 8068 0003  .h4.C@hd2.@..h..
000000b0: 4680 0680 00d0 3400 01f0 e181 0e19 58b7  F.....4.......X.
000000c0: a492 c764 0e42 1aa1 4761 42a6 7e36 03a7  ...d.B..GaB.~6..
000000d0: 563b a91b 08e0 3441 fd12 4766 1db3 8000  V;....4A..Gf....
000000e0: b7cd 8cb2 3eb6 b219 47e8 030b e560 77a5  ....>...G....`w.
000000f0: 42e9 ea78 1029 f042 9de1 d7ad 8b0b 7805  B..x.).B......x.
00000100: 6be3 7c06 df49 179b 46f6 9d44 7380 b4ed  k.|..I..F..Ds...
00000110: c2ee 1004 e33e 52dd 3422 4408 cb5e 6493  .....>R.4"D..^d.
00000120: 1495 2150 5ee7 6790 21d0 2985 e79c e2d1  ..!P^.g.!.).....
00000130: ced4 4f5e c5f6 d6d9 18de 31f1 f5d1 4946  ..O^......1...IF
00000140: 9509 37d0 6bf0 4678 9d1b d0ca 6911 eb2c  ..7.k.Fx....i..,
00000150: 9a32 903d 9e05 116c ad20 5bed c8c4 b546  .2.=...l. [....F
00000160: 9137 9a59 7858 c348 46a4 a03b a5a8 9aa7  .7.YxX.HF..;....
00000170: 941f 93c5 8881 6001 6e25 042c 7464 3b50  ......`.n%.,td;P
00000180: 4641 5475 1c33 b1c3 e553 d8a9 595f dc6c  FATu.3...S..Y_.l
00000190: 12f2 bd02 f32d 83b9 6531 880d 3cb0 9741  .....-..e1..<..A
000001a0: 56e9 509d 4964 f6da 4a2d b5a4 ea53 6527  V.P.Id..J-...Se'
000001b0: c01e 7981 095f 31c1 8446 c974 a5f9 235e  ..y.._1..F.t..#^
000001c0: a168 61f0 5822 6c3d f65d 10d1 1fd9 6677  .ha.X"l=.]....fw
000001d0: c9e4 8844 8c5a 6f2c 1041 0b42 8014 0a08  ...D.Zo,.A.B....
000001e0: 188a fa0c fa8b f7ad 3433 0840 7765 5298  ........43.@weR.
000001f0: 4937 8e7d 851f d8f2 8712 3876 3911 e2f1  I7.}......8v9...
00000200: e648 3b75 4825 e27d e424 ff1a 690b 854b  .H;uH%.}.$..i..K
00000210: 4ceb d012 31a5 12f9 fb10 9ce7 ead9 3298  L...1.........2.
00000220: fdeb 76f4 f8fa 2996 7ce1 529c 69c6 0762  ..v...).|.R.i..b
00000230: 07ea ef20 9594 41a6 4e9f fc5d c914 e142  ... ..A.N..]...B
00000240: 41ed 3e59 7c                             A.>Y|
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv compressed_fata compressed_data.bz2
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data.bz2  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ bzip2 -d compressed_data.bz2
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv compressed_data compressed_data.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ gzip -d compressed_data.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd compressed_data | head
00000000: 6461 7461 352e 6269 6e00 0000 0000 0000  data5.bin.......
00000010: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000020: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000030: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000040: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000050: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000060: 0000 0000 3030 3030 3634 3400 3030 3030  ....0000644.0000
00000070: 3030 3000 3030 3030 3030 3000 3030 3030  000.0000000.0000
00000080: 3030 3234 3030 3000 3134 3432 3132 3731  0024000.14421271
00000090: 3434 3700 3031 3132 3436 0020 3000 0000  447.011246. 0...
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv compressed_data compressed_data.tar
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ tar -xf compressed_data.tar
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data.tar  data5.bin  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd data6.bin
00000000: 425a 6839 3141 5926 5359 4911 0aa4 0000  BZh91AY&SYI.....
00000010: 8c7f dfdc 5c80 40c0 eff7 e002 f1a3 8074  ....\.@........t
00000020: 21fe 0000 0800 1002 0000 7282 0400 8442  !.........r....B
00000030: 0820 0094 0d4a 6c93 4018 8d19 1b53 4003  . ...Jl.@....S@.
00000040: 3480 69a6 3246 41a4 a36a 6269 a308 d062  4.i.2FA..jbi...b
00000050: 310c 2646 9a62 069a 014f 06ae 7e20 4066  1.&F.b...O..~ @f
00000060: 3804 081c da02 41d0 9201 830b e620 407b  8.....A...... @{
00000070: 9ce1 0374 c522 313c b2ae c856 0e88 d766  ...t."1<...V...f
00000080: 10aa 15b4 4317 1659 7002 776c 0e85 d504  ....C..Yp.wl....
00000090: 4bb4 582c 0c08 288c c166 1858 b7cd e44d  K.X,..(..f.X...M
000000a0: 3b87 555e 1268 a4d1 89a0 8272 0f89 3ea2  ;.U^.h.....r..>.
000000b0: 7140 de12 2979 c7a7 c32c d9ed 8b21 fa2a  q@..)y...,...!.*
000000c0: a527 7694 a655 7d6c f5ac 3f57 5ba6 2020  .'v..U}l..?W[.
000000d0: 1fc5 dc91 4e14 2412 4442 a900            ....N.$.DB..
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ bzip2 -d data6.bin
bzip2: Can't guess original name for data6.bin -- using data6.bin.out
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data.tar  data5.bin  data6.bin.out  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ tar -xf data6.bin.out
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data.tar  data5.bin  data6.bin.out  data8.bin  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ xxd data8.bin
00000000: 1f8b 0808 2773 4564 0203 6461 7461 392e  ....'sEd..data9.
00000010: 6269 6e00 0bc9 4855 2848 2c2e 2ecf 2f4a  bin...HU(H,.../J
00000020: 51c8 2c56 284f 0a4f c971 aa70 cd2c 3271  Q.,V(O.O.q.p.,2q
00000030: 4e74 b5f0 490c c848 2c2d f5cf 372b 280f  Nt..I..H,-..7+(.
00000040: ca2d 7229 e702 00dc ec75 4731 0000 00    .-r).....uG1...
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ gzip -d data8.gz
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ ls
compressed_data.tar  data5.bin  data6.bin.out  data8  hexdump_data
bandit12@bandit:/tmp/tmp.eCyZitnDCP$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/tmp.eCyZitnDCP$
```
## Notas adicionales
tar - Es una utilidad que se utiliza para crear, gestionar y manipular archivos en formato de archivo tar "tape archive" (archivo en cinta)
- `tar -cvf archivo.tar archivos` - Crea un archivo tar llamado "archivo.tar" que contiene los archivos especificados.
- `tar -xvf archivo.tar` - Extrae los archivos de un archivo tar.
- `tar -tvf archivo.tar` - Muestra una lista de archivos en un archivo tar.
- `tar -cvzf archivo.tar.gz archivos` - Crea un archivo tar y lo comprime en formato gzip.
- `tar -xvzf archivo.tar.gz` - Extrae un archivo tar comprimido en formato gzip.
- `tar -cvjf archivo.tar.bz2 archivos` - Crea un archivo tar y lo comprime en formato bzip2.
- `tar -xvjf archivo.tar.bz2` - Extrae un archivo tar comprimido en formato bzip2.
gzip - Se utiliza para comprimir archivos y reducir su tamaño.
- `gzip archivo` - Comprime el archivo especificado y crea un archivo con la extensión ".gz".
- `gzip -d archivo.gz` o `gunzip archivo.gz` - Descomprime un archivo comprimido.
- `gzip -c archivo > archivo.gz` - Comprime un archivo y redirige la salida al archivo comprimido.
- `gzip -l archivo.gz` - Muestra información sobre el archivo comprimido, como el tamaño original y el tamaño comprimido.
bzip2 - Se utiliza para comprimir y descomprimir archivos utilizando el algoritmo de compresión Burrows-Wheeler. Al igual que `gzip`, `bzip2` se utiliza para reducir el tamaño de los archivos y ahorrar espacio en el almacenamiento o para facilitar la transferencia de archivos a través de la red.
- `bzip2 archivo` - Comprime el archivo especificado y crea un archivo con la extensión ".bz2".
- `bzip2 -d archivo.bz2` o `bunzip2 archivo.bz2` - Descomprime un archivo comprimido.
- `bzip2 -c archivo > archivo.bz2` - Comprime un archivo y redirige la salida al archivo comprimido.
- `bzip2 -l archivo.bz2` - Muestra información sobre el archivo comprimido, como el tamaño original y el tamaño comprimido.
xxd - Realiza la conversión hexadecimal (y viceversa) de archivos binarios. La herramienta `xxd` permite mostrar el contenido de un archivo en formato hexadecimal, así como convertir el contenido hexadecimal nuevamente a su forma binaria original.
* **Ver el contenido hexadecimal de un archivo:** xxd archivo  
* **Convertir un archivo binario a formato hexadecimal:** xxd -p archivo
* **Convertir un archivo hexadecimal de vuelta a su formato binario:** xxd -r -p archivo_hexadecimal > archivo_binario
* **Editar un archivo hexadecimal:** xxd -r archivo_hexadecimal > archivo_editado
mkdir - Crea nuevos directorios (carpetas) en el sistema de archivos. El nombre "mkdir" proviene de "make directory" (crear directorio).
cp - Copiar archivos o directorios de un lugar a otro: cp [opciones] origen destino
- `-r` o `--recursive`: Copia directorios de forma recursiva (junto con su contenido).
- `-i` o `--interactive`: Solicita confirmación antes de sobrescribir un archivo existente.
- `-u` o `--update`: Copia solo cuando el archivo de origen es más nuevo que el archivo de destino o cuando el archivo de destino no existe.
- `-v` o `--verbose`: Muestra un mensaje para cada archivo copiado
mv - Mover (renombrar) archivos y directorios. También se utiliza para cambiar la ubicación de un archivo o directorio en el sistema de archivos. mv origen destino

## Referencias
[Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)
