## Descripcion
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/d2e2ce5be3c6983378013b304e34bbcfe51617a2f3ec987437028efbdbd93c83/VaultDoor3.java)
## Solucion
El reto nos da este codigo:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/reversing]
└─$ cat VaultDoor3.java
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
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
        return s.equals("jU5t_a_sna_3lpm13gf49_u_4_m9r540");
    }
}
```
entonces la contraseña al parecer esta revuelta, para ordenarla usamos este script:
```
target = "jU5t_a_sna_3lpm13gf49_u_4_m9r540"
password = [''] * 32

for i in range(8):
    password[i] = target[i]
for i in range(8, 16):
    password[23-i] = target[i]
for i in range(16, 32, 2):
    password[46-i] = target[i]
for i in range(17, 32, 2):
    password[i] = target[i]

print("picoCTF{" + "".join(password) + "}")
```
y obtenemos la bandera:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/reversing]
└─$ python vd3.py
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_99f530}
```
## Notas
- 
## Referencias
- 