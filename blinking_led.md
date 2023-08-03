# Raspberry Pi LED Blinking Project

This repository contains instructions for a simple Raspberry Pi project that involves blinking an LED.

## Materials

1. Raspberry Pi
2. Breadboard
3. LED (any color)
4. 220-ohm resistor
5. Jumper wires
6. MicroSD card with Raspberry Pi OS installed

## Python Installation

Python comes pre-installed on most versions of the Raspberry Pi OS. You can check if Python is installed and see its version by opening a terminal and typing:
"Thonny" is also an IDE for Python.

```bash
python3 --version
```
```bash
sudo apt update

```
```bash
sudo apt install python3

```
```bash
sudo apt install python3-pip

```

## Create your blink code

1. **Name your python file "blink.py"

2. **Enter the following code**

```python

import RPi.GPIO as GPIO
import time

# Use the Broadcom SOC channel
GPIO.setmode(GPIO.BCM)

# Set up GPIO 7 as an output
GPIO.setup(7, GPIO.OUT)

# Blink the LED
while True:
    GPIO.output(7, GPIO.HIGH) # LED on
    time.sleep(1) # delay for 1 second
    GPIO.output(7, GPIO.LOW) # LED off
    time.sleep(1) # delay for 1 second
```
4. **Save your python script and run it using the following command:**

```python
python3 blink.py
```

## Setting up the circuit
1. ** Connect the longer leg of the LED (the anode) to one end of the resistor.**
2. **Connect the other end of the resistor to GPIO pin 18 on the Raspberry Pi.**
3. **Connect the shorter leg of the LED (the cathode) to a GND pin on the Raspberry Pi.**


