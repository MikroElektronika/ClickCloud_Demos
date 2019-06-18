![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for Vacuum Click

---

- **CIC Prefix**  : G2C_VACUUM
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2638/vacuum-click-cloud-demo

---
#### Package link
---

- **Vacuum package**   : https://libstock.mikroe.com/projects/view/2572/vacuum-click
- **G2C package**       : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Vacuum click measures the percentage of Vacuum and the Vacuum value in %
  is sent to the cloud by reference VACUUM_P every 1500ms.   


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    float Vacuum;
	
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
    if( taskTime > 1500 )
    {
        taskTime = 0;
		
		Vacuum = vacuum_getPercentageOfVacuum();
        FloatToStr(Vacuum, demoBuffer);
		
        g2c_packCmd( &_AT_DSET[0], &Vacuum_ref[0], &demoBuffer[0]);
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
| YES | NO | VACUUM_P | % | 0 | 100 | 
---
