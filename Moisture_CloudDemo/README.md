![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for Moisture Click

---

- **CIC Prefix**  : G2C_MOISTURE
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2639/moisture-click-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **Moisture package**     : https://libstock.mikroe.com/projects/view/2433/moisture-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Moisture click reads moisture data and the data value
  is sent to the cloud by reference MOISTURE_H every 1500ms.  


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    uint8_t moistureData;
	
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
	if( taskTime > 1500 )
    {
        taskTime = 0;

        moistureData = moisture_getData();
        WordToStr(moistureData, demoBuffer);
		Ltrim(demoBuffer);
		
        g2c_packCmd( &_AT_DSET[0], &Moisture_ref[0], &demoBuffer[0]);
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
| YES | NO | MOISTURE_P | % | 0 | 100 | 
---
