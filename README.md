
### Designing a gesture-controlled lock using Arduino
> Component used in this project
### Hardware components
Spark Fun APDS - 9960
Arduino UNO & Genuino UNO
RGB Diffused Common Cathode
Adafruit Standard LCD – 16 x 2 White on Blue
Resistor 4.75k ohm
Jumper wires (generic)
Resistor 1k ohm
Software and online services
Arduino IDE

> Note that:
The APDS-9960 sensor does not work with the Arduino Nano or Mega 2560 (in my testing).

This project is easy to make and use. Feel free to use any kind of servo or latching mechanism with this project. This is meant to be a starting platform for a gesture-based lock. Onto building!
Materials

I got most of my some of my hardware components from Jumia Kenya and the APDS-9960 sensor from Spark fun. We could only use an Arduino Uno or Micro 3.3v, as any other board won't work for some odd reason.
Assembly

Attach the LCD as shown. If you don't have a 10k potentiometer, use a 1k resistor going from contrast to GND. The APDS-9960 sensor will need to be shifted if using the Arduino Uno, so what I did is take the SCL and SDA and connect them to a 4.7k resistor, then draw them high by taking the 4.7k resistor to 3.3v. Then connect them to A4 and A5, accordingly (see schematic). The Arduino can run off of a 9v battery with a DC power barrel attached.
> Enclosure

I used a simple cardboard box and cut holes out of it to match where the components would go. You could solder this all to a piece of board, but I just left it in the breadboard and connected jumper wires to the components. After I was finished, it looked like this.
> Schematic
<img src="https://media.giphy.com/media/3o7qE1YN7aBOFPRw8E/giphy.gif" width="300" height="200" />
### Arduino Code: written in C++
    code shown in the above file 
