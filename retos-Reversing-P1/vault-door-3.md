### vault-door-3
## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/943ea40e3f54fca6d2145fa7aadc5e09/VaultDoor3.java)
## Solución 
```java
// El código tiene esta función.

public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");

        System.out.println(buffer);
    }
/**
Manualmente esto no es divertido.

Así que simplemente agregue una declaración de impresión para vaciar el búfer.

Luego le puse una cuerda para que fuera una simple sustitución del cesador.
**/
picoCTF{abcdefghijklmnopqrstuvwxyz1234567}

abcdefghponmlkji5r3t1vyxwzu2s4q6

/**
Luego solo tuve que usar la matriz en el código para intercambiar cosas.
**/
jU5t_a_sna_3lpm1dg347_u_4_mfr54b

```
## Notas adicionales
picoCTF{jU5t_a_sna_3lpm18gb41_u_4_mfr340}
## Referencias