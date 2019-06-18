![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for SensorGeneric Click

---

- **CIC Prefix**  : G2C_SENSORGENERIC
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2640/sensor-generic-cloud-demo

---
#### Package link
---

- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**
  
- This project is a generic project that serves for quick and easy connection of the click to the cloud.
  It is necessary to edit the project and add parts of your click code to make it possible to connect click to the cloud.
  Use this example when you want a new click (sensor) to connect to a cloud.

```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    
// CORE STATE MACHINE
    g2c_process();

	if( taskTime > 1500 )
    {
        taskTime = 0;
        // Click task
        
		
        g2c_packCmd( &_AT_DSET[0], &SensorGeneric_ref[0], &demoBuffer[0]);
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
| YES | NO | GENERIC_REF | / | / | / | 
---
