## Descripcion
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc fickle-tempest.picoctf.net 57297.
## Solucion
entramos al server del reto y obtenemos el siguiente mensaje:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc fickle-tempest.picoctf.net 57297
-------------------------------------------------------------------------------
gcsuwmdp iewe qp tcbw zkmu - zweybesgt_qp_g_cfew_kmxhom_omg18625
-------------------------------------------------------------------------------
mkevet ztcocwcfqdgi nmwmxmrcf lmp die diqwo pcs cz ztcocw jmfkcfqdgi nmwmxmrcf, m kmso clsew lekk nscls qs cbw oqpdwqgd qs iqp cls omt, mso pdqkk wexexheweo mxcsu bp clqsu dc iqp ukccxt mso dwmuqg oemdi, liqgi imjjeseo diqwdees temwp muc, mso liqgi q pimkk oepgwqhe qs qdp jwcjew jkmge. zcw die jwepesd q lqkk cskt pmt dimd diqp kmsoclsewzcw pc le bpeo dc gmkk iqx, mkdicbui ie imwokt pjesd m omt cz iqp kqze cs iqp cls epdmdelmp m pdwmsue dtje, ted cse jweddt zweybesdkt dc he xed lqdi, m dtje mhaegd mso fqgqcbp mso md die pmxe dqxe pespekepp. hbd ie lmp cse cz dicpe pespekepp jewpcsp lic mwe fewt lekk gmjmhke cz kccnqsu mzdew dieqw lcwkokt mzzmqwp, mso, mjjmwesdkt, mzdew scdiqsu ekpe. ztcocw jmfkcfqdgi, zcw qspdmsge, heums lqdi sevd dc scdiqsu; iqp epdmde lmp cz die pxmkkepd; ie wms dc oqse md cdiew xes'p dmhkep, mso zmpdeseo cs diex mp m dcmot, ted md iqp oemdi qd mjjemweo dimd ie imo m ibsoweo dicbpmso wcbhkep qs imwo gmpi. md die pmxe dqxe, ie lmp mkk iqp kqze cse cz die xcpd pespekepp, zmsdmpdqgmk zekkclp qs die licke oqpdwqgd. q wejemd, qd lmp scd pdbjqoqdtdie xmacwqdt cz diepe zmsdmpdqgmk zekkclp mwe piwelo mso qsdekkquesd escbuihbd abpd pespekeppsepp, mso m jegbkqmw smdqcsmk zcwx cz qd.
```
el cifrado por sustitucion es un metodo de cifrado donde las unidades de texto plano como letras son reemplazadas con simbolos u otras letras basadas en una llave, entramos a la siguiente [pagina](https://www.guballa.de/substitution-solver) y ponemos el mensaje, presionamos break cipher y obtenemos este mensaje decodificado:
```
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_dac18625
-------------------------------------------------------------------------------
alexey fyodorovitch karamazov was the third son of fyodor pavlovitch karamazov, a land owner well known in our district in his own day, and still remembered among us owing to his gloomy and tragic death, which happened thirteen years ago, and which i shall describe in its proper place. for the present i will only say that this landownerfor so we used to call him, although he hardly spent a day of his life on his own estatewas a strange type, yet one pretty frequently to be met with, a type abject and vicious and at the same time senseless. but he was one of those senseless persons who are very well capable of looking after their worldly affairs, and, apparently, after nothing else. fyodor pavlovitch, for instance, began with next to nothing; his estate was of the smallest; he ran to dine at other men's tables, and fastened on them as a toady, yet at his death it appeared that he had a hundred thousand roubles in hard cash. at the same time, he was all his life one of the most senseless, fantastical fellows in the whole district. i repeat, it was not stupiditythe majority of these fantastical fellows are shrewd and intelligent enoughbut just senselessness, and a peculiar national form of it.
```
la bandera queda asi: frequency_is_c_over_lambda_dac18625
## Notas
- 
## Referencias
- 