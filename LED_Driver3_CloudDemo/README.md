![MikroE](http://www.mikroe.com/img/designs/beta/logo_small.png)

---

# Cloud demo for LED_Driver3 Click

---

- **CIC Prefix**  : G2C_LEDDRIVER3
- **Author**      : Katarina Perendic
- **Verison**     : 1.0.0
- **Date**        : nov 2018.

---

- **Libstock** : https://libstock.mikroe.com/projects/view/2644/led-driver-3-click-cloud-demo

---
#### Package link
---

- **LED_Driver3 package ** : https://libstock.mikroe.com/projects/view/2301/led-driver-3-click
- **G2C package**           : https://libstock.mikroe.com/projects/view/2628/g2c-click

---

**Examples Description**

- The example contains all the necessary initializations and 
  settings for a G2C click on a successful connection by Click Cloud.
- Led Driver 3 click (actuator) Turns ON LEDs on the color that is settings on the Cloud.
- This example demonstrate using the Actuator(string) parser. 


```.c
void applicationTask()
{
    char demoBuffer[ 50 ];
    
// CORE STATE MACHINE
    g2c_process();

    if(newText == 1)
    {
        if(color == 0)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_RED);
        }
        if(color == 1 )
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_GREEN);
        }
        if(color == 2)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_BLUE);
        }
        if(color == 3)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_YELLOW);
        }
        if(color == 4)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_PURPLE);
        }
        if(color == 5)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_ORANGE);
        }
        if(color == 6)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_WHITE);
        }
        if(color == 7)
        {
            leddriver3_setColor(_LEDDRIVER3_COLOR_OFF);
        }
        newText = 0;
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
| NO | YES | LEDDRIVER3_CLR | String | x | x | 

---
