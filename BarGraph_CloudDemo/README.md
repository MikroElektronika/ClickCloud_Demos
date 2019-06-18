![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for BarGraph Click

---

- **CIC Prefix**  : G2C_BARGRAPH
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2643/bargraph-click-cloud-demo
- **GitHub**   : ${GITHUB_LINK}

---
#### Package link
---

- **BarGraph package **     : https://libstock.mikroe.com/projects/view/631/bargraph-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- BarGraph click (actuator) displays value of the counter that is settings on the Cloud.
- This example demonstrate using the Actuator(counter) parser. 

```.c
void applicationTask()
{

// CORE STATE MACHINE
    g2c_process();

    if(bargraph_counter >= 0 && bargraph_counter <= 10)
    {
        bargraph_display( bargraph_counter );
    }
}
```
---
### Architectures Supported

#### mikroC

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x |   | x | x | x | x | x | x |
---

#### mikroBasic

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x |   | x | x | x | x | x | x |
---

#### mikroPascal

| STM | KIN | CEC | MSP | TIVA | PIC | PIC32 | DSPIC | AVR | FT90x |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| x | x | x |   | x | x | x | x | x | x |
---

#### Cloud

| Sensor | Actuator | Reference | Measurement unit | Range - min  | Range - max |
|:------:|:--------:|:-----:|:-----:|:------------:|:-----------:|
| NO | YES | BARGRAPH_CNT | counter | 0 | 10 | 

---
