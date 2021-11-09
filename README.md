#   Conversor Digital Analógico - DAC  
  *  Utilizando uma rede de risistores R2R criaremos  um DAC de 4 bits 


![CIRCUITO_R2R](https://user-images.githubusercontent.com/60757810/140799990-6f2149e9-0ffb-4bb0-9d9a-1ffa61e28482.PNG)


# Gerando Sinais com o DAC 

 ## Rampa -4 bits

* Código MBED 

```javascript

//**********************Rampa DAC 4 bits**************************************//
#include "mbed.h"

BusOut saida(D9,D8,D7,D6);



int main()
{
    while(1) {
        for (int i =  0; i<=15; i++) {
            saida = i;

            wait(0.01);
        }
    }
}

//****************************************************************************//

```

![Rampa](https://user-images.githubusercontent.com/60757810/140803060-6049bfea-db22-426a-99b6-ca966c55cf7f.PNG)


## Triangular 

* Código MBED 

```javascript

//**********************Triangular DAC 4 bits**************************************//
#include "mbed.h"

BusOut saida(D9,D8,D7,D6);


int main()
{
   int k;
    while(1) { 
        for(k = 0; k < 15; k++) { 
            saida = k; 
            wait_us(100.0); 
        }
        for(k = 15; k > 0; k = k--) { 
            saida = k; 
            wait_us(100.0); 
        }
    }
}


//****************************************************************************//

```
![Triangular](https://user-images.githubusercontent.com/60757810/140912560-b5479726-cdc6-4b34-bdf7-07ae94c10018.PNG)


