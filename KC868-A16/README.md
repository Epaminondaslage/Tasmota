# Tasmota firmware with KC868-A16

* Foram feitos todas as tentativas disponibilizadas no site de suporte da KinConi e a UI nao funcionou corretamente. O mais significativo foi o fato dos firmawares disponibilizados pelo fabricante **não** suportarem as atualizações do firmware Tasmota conforme são disponibilizadas pelo fabricante do Sw.

* Referencias não testadas no site Tasmota https://templates.blakadder.com/kincony_KC868-A16.html


### Config do template para ESP32:

```
{"NAME":"KC868-A16 rev 1.4","GPIO":[32,1,1,1,640,608,1,1,1,1,1,1,1,1,5600,1,0,1,1,5568,0,1,1,1,0,0,0,0,1,1,1,1,1,0,0,1],"FLAG":0,"BASE":1}

```
---
Use the _USB-C_ port to flash the device.

### To build a binary with ethernet, all inputs and outputs support add to `user_config_override.h`:

```arduino
#ifndef USE_I2C
#define USE_I2C                                  // I2C using library wire (+10k code, 0k2 mem, 124 iram)
#endif

  #define USE_PCF8574                            // [I2cDriver2] Enable PCF8574 I/O Expander (I2C addresses 0x20 - 0x26 and 0x39 - 0x3F) (+1k9 code)
    #define USE_PCF8574_SENSOR                   // enable PCF8574 inputs and outputs in SENSOR message
    #define USE_PCF8574_DISPLAYINPUT             // enable PCF8574 inputs display in Web page
    #define USE_PCF8574_MQTTINPUT                // enable MQTT message & rule process on input change detection : stat/%topic%/PCF8574_INP = {""Time"":""2021-03-07T16:19:23+01:00"",""PCF8574-1_INP"":{""D1"":1}}

#define USE_ETHERNET                             // Add support for ethernet (Currently fixed for Olimex ESP32-PoE)
  #define ETH_TYPE          0                    // [EthType] 0 = ETH_PHY_LAN8720, 1 = ETH_PHY_TLK110, 2 = ETH_PHY_IP101
  #define ETH_ADDR          0                    // [EthAddress] 0 = PHY0 .. 31 = PHY31
  #define ETH_CLKMODE       3                    // [EthClockMode] 0 = ETH_CLOCK_GPIO0_IN, 1 = ETH_CLOCK_GPIO0_OUT, 2 = ETH_CLOCK_GPIO16_OUT, 3 = ETH_CLOCK_GPIO17_OUT
```

Inputs (X01 - X16) and outputs (Y01 - Y16) use [PCF8574](https://tasmota.github.io/docs/PCF8574/) over I2C. 

You need to configure them using _

**Configuration - Configure PCF8574**_ and set

- Device 1  Port 0 - Port 7 as Output
- Device 2  Port 0 - Port 7 as Output
- Device 3  Port 0 - Port 7 as Input
- Device 4  Port 0 - Port 7 as Input

[KinCony forums](https://www.kincony.com/forum/forumdisplay.php?fid=6) have examples and demos of all the functions with various firmware

[Schematics](https://www.kincony.com/download/KC868-A16-schematic.pdf)

RF Transmitter and Receiver not tested
