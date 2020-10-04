
### Designing a gesture-controlled lock using Arduino
> Realworld Application

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
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/09264-1.jpg" />
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/11026-02.jpg" />
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/181-02.jpg" />
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/A000066_iso_both.jpg" />
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/IDE_web.jpg" />
<img align="left" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/MFR-25FBF52-4K75_sml.jpg" />
<img align="" alt="" width="60px" src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/components/MFR-25FRF52-1K_sml.jpg" />

> Note that:
  The APDS-9960 sensor does not work with the Arduino Nano or Mega 2560 (in my testing).

This project is cheap, and easy to implement. Feel free to use any kind of servo or latching mechanism with this project. This is meant to be a starting platform for a gesture-controlled lock.

    I got most of my hardware components from Jumia Kenya and the APDS-9960 sensor from Spark fun.
    We could only use an Arduino Uno or Micro 3.3v, as any other board won't work for some odd reason.
> Assembling procedure

    - Connect the LCD in board as illustrated in the schematic below.
    - If you don't have a 10k potentiometer, use a 1k resistor and connect it to the GND. 
    - The APDS-9960 sensor need to be slightly shifted when using the Arduino Uno.
    - Connect SCL and SDA to a 4.7k resistor. Inorder to draw power connect 4.7k resistor to high 3.3v.
    - Connect them to A4 and A5, accordingly as shown in the schematic below. 
    - The Arduino can run off of a 9v battery with a DC power barrel attached.
> Enclosure

    I used a simple cardboard box and cut holes out of it to match where the components would go.
    You could solder this all to a piece of board, but I just left it in the breadboard
    and connected jumper wires to the components.
  
> Schematic

Used to guide us when connecting the components

<img src="https://raw.githubusercontent.com/danielmuthama/Gesture-controlled-lock-in-Arduino/master/schematic_bb3_ojGtzuoycT.png" width="500" height="400" />

### Arduino Code: written in C++
   > Code present in the file below 
   
    #include <Keypad.h>
    #include <LiquidCrystal.h>
    #include <Servo.h>
    Servo myservo;

    LiquidCrystal lcd(A0, A1, A2, A3, A4, A5);
    #define Password_Lenght 7 // Give enough room for six chars + NULL char
    int pos = 0;    // variable to store the servo position
    char Data[Password_Lenght]; // 6 is the number of chars it can hold + the null char = 7
    char Master[Password_Lenght] = "123456";
    byte data_count = 0, master_count = 0;
    bool Pass_is_good;
    char customKey;
    const byte ROWS = 4;
    const byte COLS = 3;
    char keys[ROWS][COLS] = {
    {'1', '2', '3'},
    {'4', '5', '6'},
    {'7', '8', '9'},
    {'*', '0', '#'}
    };
    
   ![Arduinominiproject.mm](https://github.com/danielmuthama/Gesture-controlled-lock-in-Arduino/blob/master/Arduinominiproject.mm)
