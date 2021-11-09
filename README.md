#   Conversor Digital Analógico - DAC  
  *  Utilizando uma rede de risistores R2R criaremos  um DAC de 4 bits 


![CIRCUITO_R2R](https://user-images.githubusercontent.com/60757810/140799990-6f2149e9-0ffb-4bb0-9d9a-1ffa61e28482.PNG)


# Gerando Sinais com o DAC 

 ## Rampa - 4 bits

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


## Triangular - 4 bits

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
![Triangular](https://user-images.githubusercontent.com/60757810/140933501-dcbabf79-e754-42b5-a1fc-bb5f0a387399.PNG)


## Senoide  - 4 bits
 

![Senoide](https://user-images.githubusercontent.com/60757810/140930844-4860e527-b22f-4664-b3e1-9695afe07e93.PNG)

# DAC - 8 Bits 
 *  Agora montaremos  um DAC de 8 bits 

![circuito 8bits](https://user-images.githubusercontent.com/60757810/140934968-afa3646d-f03c-4686-a6a1-3451c33cc3bc.PNG)

 ## Rampa - 8 bits

* Código MBED 

```javascript

//**********************Rampa DAC 8 bits**************************************//
#include "mbed.h"

BusOut saida(D9,D8,D7,D6,D5,D4,D3,D2);



int main()
{
    while(1) {
        for (int i =  0; i<=256; i++) {
            saida = i;

            wait_us(100.0);
        }
    }
}

//****************************************************************************//

```

![Rampa_8bits](https://user-images.githubusercontent.com/60757810/140937568-a8600153-6708-4666-8c81-2095e8430a1d.PNG)

 ## Triangular - 8 bits

* Código MBED 
```javascript
/**********************Triangular DAC 8 bits*********************************//

#include "mbed.h"

BusOut saida(D9,D8,D7,D6,D5,D4,D3,D2);


int main()
{
   int k;
    while(1) { // Do forever
        for(k = 0; k < 255;k = k+1) { // Do 100 times
            saida = k; 
            wait_us(100.0); // Wait 100us
        }
        for(k = 255; k > 0; k = k-1) { // Do 100 times
            saida = k; // Analog out
            wait_us(100.0); // Wait 100us
        }
    }
}

//****************************************************************************//

```
![Triangular_8bits](https://user-images.githubusercontent.com/60757810/140939580-6ff8c0c6-4798-4786-80c9-786387e3bedf.PNG)
