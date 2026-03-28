## Descripcion
After logging in, you will find multiple file parts in your home directory. These parts need to be combined and extracted to reveal the flag. SSH to `dolphin-cove.picoctf.net`:`53589` and login as `ctf-player` with password `fa005713`.

ssh -p 53589 ctf-player@dolphin-cove.picoctf.net 
## Solucion
```
ctf-player@pico-chall$ ls
instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ cat instructions.txt
Hint:

- The flag is split into multiple parts as a zipped file.
- Use Linux commands to combine the parts into one file.
- The zip file is password protected. Use this "supersecret" password to extract the zip file.
- After unzipping, check the extracted text file for the flag.


ctf-player@pico-chall$ cat part_a* > flag.zip
ctf-player@pico-chall$ ls
flag.zip  instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ unzip flag.zip
Archive:  flag.zip
[flag.zip] flag.txt password:
 extracting: flag.txt
ctf-player@pico-chall$ ls
flag.txt  flag.zip  instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ cat flag.
cat: flag.: No such file or directory
ctf-player@pico-chall$ cat flag.txt
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_8fa833a5}
ctf-player@pico-chall$

```
## Notas
- 
## Referencias
- 