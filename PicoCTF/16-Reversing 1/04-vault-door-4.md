## Descripcion
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/dfb236ca8b03fc1044ad906ce94fd2ed85beb1d1118f09234607b5f79d4b72fc/VaultDoor4.java)
## Solucion
en esta ocasion el codigo del reto es este:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/reversing]
└─$ cat VaultDoor4.java
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 066 , 064 ,
            'e' , '1' , '3' , 'd' , '0' , '0' , 'b' , '2' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
```
en el codigo vienen varios valores en diferentes formatos como hexadecimal, octal y decimal, entonces debemos hacer las conversiones.

primero la [conversion](https://gchq.github.io/CyberChef/#recipe=From_Decimal('Comma',false)&input=MTA2ICwgODUgICwgNTMgICwgMTE2ICwgOTUgICwgNTIgICwgOTUgICwgOTg) de decimal a su equivalente en ASCII:jU5t_4_b

[conversion](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg1NSwweDZlLDB4NDMsMHg2OCwweDVmLDB4MzAsMHg2NiwweDVm) de hexa a ASCII: UnCh_0f_

[conversion](https://gchq.github.io/CyberChef/#recipe=From_Octal('Comma')&input=MDE0MiwgMDEzMSwgMDE2NCwgMDYzICwgMDE2MywgMDEzNywgMDY2ICwgMDY0) de octal a ASCII: bYt3s_64

y al final solo unimos los caracteres: e13d00b2

entonces la bandera queda asi:
picoCTF{jU5t_4_bUnCh_0f_bYt3s_64e13d00b2}


## Notas
- 
## Referencias
- 