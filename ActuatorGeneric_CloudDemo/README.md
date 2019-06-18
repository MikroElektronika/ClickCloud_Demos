![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for ActuatorGeneric Click

---

- **CIC Prefix**  : G2C_ACTUATORGENERIC
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2641/actuator-generic-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- It is necessary to edit the project and add parts of your click code to make it possible to connect click to the cloud.
  Use this example when you want a new click (actuator) to connect to a cloud.


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    
// CORE STATE MACHINE
    g2c_process();
	
// ACTUATOR DEMO
    if(state == 1 && oldstate == 0)
    {
        oldstate = 1;
        mikrobus_logWrite( "State ON", _LOG_LINE );
		// User code if the swithc is set to 1
    
    }
    if(state == 0 && oldstate == 1)
    {
        oldstate = 0;
		mikrobus_logWrite( "State OFF", _LOG_LINE );
        // User code if the swithc is set to 0
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
| NO | YES | ACTUATOR_REF | switch | 0 | 1 | 
---
