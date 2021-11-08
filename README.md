#   Conversor Digital Analógico - DAC  
  *  Utilizando uma rede de risistores R2R criaremos  um DAC de 4 bits 


![CIRCUITO_R2R](https://user-images.githubusercontent.com/60757810/140799990-6f2149e9-0ffb-4bb0-9d9a-1ffa61e28482.PNG)


# Gerando Sinais com o DAC 

 ## Rampa 

![Rampa](https://user-images.githubusercontent.com/60757810/140803060-6049bfea-db22-426a-99b6-ca966c55cf7f.PNG)

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
