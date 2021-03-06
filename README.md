# Data Logger (and using cool sensors!)

*A lab report by John Q. Student.*

## In The Report

Include your responses to the bold questions on your own fork of [this lab report template](https://github.com/FAR-Lab/IDD-Fa18-Lab2). Include snippets of code that explain what you did. Deliverables are due next Tuesday. Post your lab reports as README.md pages on your GitHub, and post a link to that on your main class hub page.

For this lab, we will be experimenting with a variety of sensors, sending the data to the Arduino serial monitor, writing data to the EEPROM of the Arduino, and then playing the data back.

## Part A.  Writing to the Serial Monitor
 
**a. Based on the readings from the serial monitor, what is the range of the analog values being read?**

0-1023
 
**b. How many bits of resolution does the analog to digital converter (ADC) on the Arduino have?**
10 bits gives you 0 -1023 discrete values, which is also equal to 5 volts. 
Every pin has a different capacity for voltage
You can also find this on the product page. 

to see serial plotter:

! (photo) [Screen Shot 2019-05-10 at 4.17.15 PM.png]
## Part B. RGB LED

**How might you use this with only the parts in your kit? Show us your solution.**

Add resistors.

## Part C. Voltage Varying Sensors 
 
### 1. FSR, Flex Sensor, Photo cell, Softpot

**a. What voltage values do you see from your force sensor?**
1 volt is analog = 200
the numbers is digital (return value) 

code is in this repository...as FSR

**b. What kind of relationship does the voltage have as a function of the force applied? (e.g., linear?)**

This is linear, while a proximity sensor would not be linear because of the reflection not being read at the same rate. 

**c. Can you change the LED fading code values so that you get the full range of output voltages from the LED when using your FSR?**

You would divide analog by 4, you would get 255

**d. What resistance do you need to have in series to get a reasonable range of voltages from each sensor?**

My answer: You push really hard and wait to see what is the highest output in the serial monitor.
Justin's Answer: It's linear and 0-1023 maps to 0-255

int scaledVoltage = map(voltageValue, 0, 1023, 0, 255);

tried but not true here: look at the threshold for the LED, below voltage threshold, no LED can light, below 1.8 volts (red) , according to the internet. Instead of 5 - 0, we should map it from 1.8 - 5. Different colors have different voltage drop. 
**e. What kind of relationship does the resistance have as a function of stimulus? (e.g., linear?)**

### 2. Accelerometer
 
**a. Include your accelerometer read-out code in your write-up.**

### 3. IR Proximity Sensor

**a. Describe the voltage change over the sensing range of the sensor. A sketch of voltage vs. distance would work also. Does it match up with what you expect from the datasheet?**

**b. Upload your merged code to your lab report repository and link to it here.**

## Optional. Graphic Display

**Take a picture of your screen working insert it here!**

## Part D. Logging values to the EEPROM and reading them back
 
### 1. Reading and writing values to the Arduino EEPROM

**a. Does it matter what actions are assigned to which state? Why?**

**b. Why is the code here all in the setup() functions and not in the loop() functions?**

**c. How many byte-sized data samples can you store on the Atmega328?**

**d. How would you get analog data from the Arduino analog pins to be byte-sized? How about analog data from the I2C devices?**

**e. Alternately, how would we store the data if it were bigger than a byte? (hint: take a look at the [EEPROMPut](https://www.arduino.cc/en/Reference/EEPROMPut) example)**

**Upload your modified code that takes in analog values from your sensors and prints them back out to the Arduino Serial Monitor.**

### 2. Design your logger
 
**a. Insert here a copy of your final state diagram.**

### 3. Create your data logger!
 
**a. Record and upload a short demo video of your logger in action.**
