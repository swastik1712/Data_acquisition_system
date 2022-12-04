# Data_acquisition_system
Hello everyone, This project about How can we use ADS1115 with STM32 and Cubemx. Firstly I want to talk about what ADS1115 is and what it does.
ADS1115 is an analog to digital converter (ADC). It is ultra small sized and has I2C communication. It has 4 channels to read analog voltages and 
transmit these voltage values via I2C communication bus. For more details you can check datasheet of ADS1115.

Now lets start with a cubemx project and configure board for ADS1115 and I2C communication. My processor is STM32F401RE and I have created project with 
this microprocessor.
After creating new cubemx project we need to acticate I2C under Connectivity section. PB7 as SDA and PB6 as SCL pin will be activated
We are choosing which channel to read in this for loop. 0xC0, 0xD0, 0xE0 and 0xF0 values provided from datasheet. These values are for selecting to channel. 
Last value of the sended variable is for choosing LSB or MSB. If we want get value as reversed. After specifing the read configurations we need to transmit 
this variable into I2C data bus and ADS1115 will read this values. After this ADS1115 will answer to our microprocessor. Then receive the answer.
Then multiply the value with voltage conversation constant and get the between 0 - 3.3 voltage value.
