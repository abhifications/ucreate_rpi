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


```python

import RPi.GPIO as GPIO
import time

# Use the Broadcom SOC channel
GPIO.setmode(GPIO.BCM)

# Set up GPIO 18 as an output
GPIO.setup(18, GPIO.OUT)

# Blink the LED
while True:
    GPIO.output(18, GPIO.HIGH) # LED on
    time.sleep(1) # delay for 1 second
    GPIO.output(18, GPIO.LOW) # LED off
    time.sleep(1) # delay for 1 second
```

