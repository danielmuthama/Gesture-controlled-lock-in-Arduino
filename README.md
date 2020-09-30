
### Designing a gesture-controlled lock using Arduino
[![Watch the video](https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/Screenshot_2020-09-29%20Webmole%200%203%20Open%20Source%20Application%20Presentation.png)](https://youtu.be/VZHX5NwCBbw)
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

This project is cheap, and easy to implement. Feel free to use any kind of servo or latching mechanism with this project. This is meant to be a starting platform for a gesture-controlled lock.

    I got most of my some of my hardware components from Jumia Kenya
    and the APDS-9960 sensor from Spark fun.
    We could only use an Arduino Uno or Micro 3.3v,
    as any other board won't work for some odd reason.
> Assembling procedure

    Connect the LCD in board as shown.
    If you don't have a 10k potentiometer, use a 1k resistor and connect it to the GND. 
    The APDS-9960 sensor need to be slightly shifted when using the Arduino Uno.
    Connect SCL and SDA to a 4.7k resistor. Inorder to draw power connect 4.7k resistor to high 3.3v.
    Connect them to A4 and A5, accordingly as shown in the schematic below. 
    The Arduino can run off of a 9v battery with a DC power barrel attached.
> Enclosure

    I used a simple cardboard box and cut holes out of it to match where the components would go.
    You could solder this all to a piece of board, but I just left it in the breadboard
    and connected jumper wires to the components.
  
> Schematic
<img src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/schematic_bb3_ojGtzuoycT.png" width="500" height="400" />

### Arduino Code: written in C++
   > Code present in the below file 
    
   ![Arduinominiproject.mm](https://github.com/danielmuthama/Gesture-controlled-lock-in-Arduino/blob/master/Arduinominiproject.mm)
