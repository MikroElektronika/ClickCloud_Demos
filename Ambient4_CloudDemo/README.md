![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for Ambient4 Click

---

- **CIC Prefix**  : G2C_AMBIENT4
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2630/ambient-4-click-cloud-demo

---
#### Package link
---

- **Ambient4 package**     : https://libstock.mikroe.com/projects/view/2582/ambient-4-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Ambient 4 click reads ambient light and the light value 
  is sent to the cloud by reference AMBIENT4_LX every 1500ms.   


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    uint16_t ambientValue;
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
    if( taskTime > 1500 )
    {
        taskTime = 0;
        ambientValue = ambient4_readData();
        WordToStr(ambientValue, demoBuffer);
        Ltrim(demoBuffer);
        
        g2c_packCmd( &_AT_DSET[0], &Ambient4_ref[0], &demoBuffer[0]);
        g2c_cmdSingle( &_AT_PUB[0] );
    }
}
```
---
### Architectures Supported

#### mikroC

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x | x | x | x | x | x | x | x |

---
#### mikroBasic

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x | x | x | x | x | x | x | x |

---
#### mikroPascal

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x | x | x | x | x | x | x | x |

---
#### Cloud

| Sensor | Actuator | Reference | Measurement unit | Range - min  | Range - max |
|:------:|:--------:|:-----:|:-----:|:------------:|:-----------:|
| YES | x | AMBIENT4_LX | lux[lx] | 0 | 65536 | 
---
