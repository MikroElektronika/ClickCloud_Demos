![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for LightRanger4 Click

---

- **CIC Prefix**  : G2C_LIGHTRANGER4
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2635/lightranger-4-click-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **LightRanger4 package**  : https://libstock.mikroe.com/projects/view/2576/lightranger-4-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- LightRanger 4 click measures the distance of the object in front of the sensor and the distance value in mm 
  is sent to the cloud by reference LIGHTRANGER4_L every 1500ms.   


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    uint16_t distance;
	
// CORE STATE MACHINE
    g2c_process();

// SENSOR DEMO
	if( taskTime > 1500 )
    {
        taskTime = 0;
        while(lightranger4_newDataReady() != 0)
        {
            Delay_1ms();
        }

        distance = lightranger4_getDistance();
        WordToStr(distance, demoBuffer);	   
        Ltrim(demoBuffer);
		
        g2c_packCmd( &_AT_DSET[0], &LightRanger4_ref[0], &demoBuffer[0]);
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
| YES | NO | LIGHTRANGER4_L | mm | 0 | 4000 | 

---
