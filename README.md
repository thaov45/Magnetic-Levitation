# Magnetic Levitation with Arduino
**Updates (Oct 2022):** Added a voltage regulator 

---
Re-created an apparatus of Magnetic Levitation with an Arduino Uno board by applying magnetics’ properties.
<a href="https://www.youtube.com/watch?v=c5Mpk-SmmZc" target="_blank">Video</a>

*A school project for Physics 2 Calculus-based class on May 2022*

---
| Materials        | Note           | 
| ------------- |:-------------:| 
| Electromagnet      |       |
| Hall effect sensor | 49E     |
| Resistor X2     |   1k Ohm  |
| Arduino Uno     |       |
| Neodymium magnet      |       |
| Transistor      |    TIP 122   |
| Voltage Regulator      |   IC 7806    |
| Power supply      |   12V    |
| LED     |  Optional  | 
---
### Schematic
![alt text](https://github.com/thaov45/magneticlevitation/blob/main/Schematic.png "Schematic")

---
### Principle
The magnet is positioned close enough to the electromagnet so that its magnetic field can interact with the magnet, but not so close that the magnet's own magnetic field is able to pull itself up to the electromagnet regardless of the power. A hall effect sensor is used to control the electromagnet so that when the magnet is too far away, the electromagnet will pull the magnet closer, but turn off when it gets too close, so that gravity can still pull it back down. It is placed underneath the electromagnet. Using the Arduino Uno, the electromagnet will turn on and off whenever the magnet passes a custom levitation point/ levitation value which is detected by the sensor. 

If the analog value is greater than the levitation value, the electromagnet turns off. If the analog value is less than the levitation value, the electromagnet turns on. 

Between each oscillation that the magnets go through, it creates a delay time between each time the electromagnet turns on and off, which creates an error overtime that does not allow the magnets to stay levitated. For this reason, a PID Controller is set to minimize the error, which maintains the magnets at the desired setpoint, or the levitation value that we set in the Arduino code.

![alt text](https://github.com/thaov45/magneticlevitation/blob/main/Untitled.png "Image 1")
![alt text](https://github.com/thaov45/magneticlevitation/blob/main/Untitled%202.png "Image 2")

