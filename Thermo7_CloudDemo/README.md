![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for Thermo7 Click

---

- **CIC Prefix**  : G2C_THERMO7
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2631/thermo-7-click-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **Thermo7 package**       : https://libstock.mikroe.com/projects/view/2367/thermo-7-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Thermo 7 click reads ambient temperature and the temperature value 
  is sent to the cloud by reference THERMO7_T every 1500ms.  


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    float AmbientTemperature;
	
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
	if( taskTime > 1500 )
    {
        taskTime = 0;

        AmbientTemperature = thermo7_readAmbientTemperature();
        FloatToStr(AmbientTemperature, demoBuffer);   
        Ltrim(demoBuffer);
        
        g2c_packCmd( &_AT_DSET[0], &Thermo7_ref[0], &demoBuffer[0]);
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
| YES | NO | THERMO7_T | C | -10 | 125 | 
---
