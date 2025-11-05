
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include <reg51.h>

void main(void)
{
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    SBUF = 'A';
    while(TI == 0);
    TI = 0;

    while(1);
}
```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "SURYA";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}
```

### OUTPUT:

<img width="808" height="424" alt="image" src="https://github.com/user-attachments/assets/dc09304a-2e10-4ad8-9fb9-ab43a311add3" />

<img width="815" height="525" alt="image" src="https://github.com/user-attachments/assets/b4485ed8-1ce7-4b4c-8739-812ab7291228" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
