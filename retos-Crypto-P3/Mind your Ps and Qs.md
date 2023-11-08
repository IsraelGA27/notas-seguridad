### Mind your Ps and Qs
## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values)
## Solución 
```shell 
Aquí está el contenido de los valores:
Decrypt my super sick RSA:
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537
```

```java
package Cryptography.javacodebad;

import java.math.BigInteger;
import java.util.ArrayList;
import java.util.Scanner;

public class RSA {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        BigInteger N,phiN,e,d,m,c;

        // cipertext c, plaintext m

        System.out.println("Insert N");
        N = new BigInteger (sc.nextLine());

        System.out.println("Input e");
        e = new BigInteger (sc.nextLine());

        System.out.println("Input c");
        c = new BigInteger (sc.nextLine());

        System.out.println("Input phi");
        phiN = new BigInteger (sc.nextLine());

        sc.close();

        d = e.modInverse(phiN);
        m = c.modPow(d, N);

        System.out.println("d = "+d);           
        System.out.println("m = "+m);

        System.out.println("m in base 256 = "+base256(m));
        System.out.println("Convert with ASCII \n"+ Encode256(base256(m)));
    }
    static ArrayList<BigInteger> base256 (BigInteger M) {
        BigInteger base = new BigInteger("256");
        ArrayList<BigInteger> message256 = new ArrayList<BigInteger>();
        BigInteger sisa=M;
        BigInteger k;
        double z = Double.parseDouble(M.toString());
        double p = Math.floor(Math.log(z)/Math.log(256));
        int r = (int) p;
        for (int j=0;j<=r;j++){
            k=sisa.mod(base);
            sisa=sisa.divide(base);
            message256.add(k);
        }
        return message256;
    }

    static String Encode256 (ArrayList<BigInteger> ascii) {
        String ascii256="";
        int g;
        for (int i=0;i<ascii.size();i++) {
            g = Integer.parseInt(""+ascii.get(i));
            ascii256=ascii256+( (char) g );
        }
        return ascii256;
    }
}
```
![[Pasted image 20231108004153.png]]
Parece que la bandera está invertida: }76721050_do0g_0n_N_11ams{FTCocip. Eso está bien, solución simple. Ejecuté un script de Python
```python
reved_string = "}76721050_do0g_0n_N_11ams{FTCocip"
flag = ""
for i in reved_string:
    flag = i + flag
print(flag)
```

## Notas adicionales
Flag: picoCTF{sma11_N_n0_g0od_05012767}
## Referencias
https://crypto.stackexchange.com/questions/19915/rsa-decryption-given-n-e-and-phin
https://www.alpertron.com.ar/ECM.HTM