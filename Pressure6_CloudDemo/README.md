![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for Pressure6 Click

---

- **CIC Prefix**  : G2C_PRESSURE6
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2634/pressure-6-click-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **Pressure6 package**    : https://libstock.mikroe.com/projects/view/2580/pressure-6-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Pressure 6 click reads temperature and pressure data and the temperature/pressure value
  is sent to the cloud by reference PRESSURE6_T/PRESSURE6_P every 1500ms.  


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    uint16_t Pressure;
    uint8_t  Temperature;
	
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
	if( taskTime > 1500 )
    {
        taskTime = 0;
                
	    pressure6_waitingForNewData();
        Pressure = pressure6_getPressure();
        Temperature = pressure6_getTemperatre();
        
        IntToStr(Pressure, demoBuffer);
		Ltrim(demoBuffer);
		g2c_packCmd( &_AT_DSET[0], &Pressure6_pressureRef[0], &demoBuffer[0]);
        
		IntToStr(Temperature, demoBuffer);
		Ltrim(demoBuffer);
        g2c_packCmd( &_AT_DSET[0], &Pressure6_temperatureRef[0], &demoBuffer[0]);
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

#### mikroBasic

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x | x | x | x | x | x | x | x |

#### mikroPascal

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x | x | x | x | x | x | x | x |

#### Cloud

| Sensor | Actuator | Reference | Measurement unit | Range - min  | Range - max |
|:------:|:--------:|:-----:|:-----:|:------------:|:-----------:|
| YES | NO | PRESSURE6_P | mbar | 300 | 1300 | 
| YES | NO | PRESSURE6_T | C | 0 | +85 | 

---
---
