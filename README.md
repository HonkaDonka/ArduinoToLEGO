# About

The LEGO Mindstorms EV3 is a robotics kit that blends the lines between LEGO and robotics. Although the EV3's Brick has limited functionality compared to Arduino microcontrollers, my transition to Arduino lacked the necessary resources for 3D printing casing parts. However, I had an abundance of LEGO bricks at my disposal. Thus, this project aims to assist others in integrating their Arduinos with EV3 motors. This not only enhances functionality but also promotes accessibility for those who already own a LEGO Mindstorms kit.

## Using an Arduino to control LEGO EV3 Motors

### How

#### Hardware Developer Manual

The [LEGO Mindstorms website](https://education.lego.com/en-us/product-resources/mindstorms-ev3/downloads/developer-kits#ev3-hardware-developer-kit) includes a hardware developer manual that shows the pinout of the motors and sensors of the EV3. 

![image](https://github.com/VinsonOi/ArduinoToLEGO/assets/30189257/bc7275f2-7d74-4d44-a0f3-d124374ff1d6)

Pins 1 and 2 function as motor direction control similar to a standard servo. For instance, setting pin 1 to HIGH and pin 2 to LOW makes the motor spin in one direction, while setting pin 1 to LOW and pin 2 to HIGH causes it to spin in the opposite direction.

Pins 5 and 6 are used for the rotary encoder, which provides information on the orientation of the motor.

#### The L293D Chip

This chip will be used to drive the motor. [This link](https://www.robotix.in/tutorial/auto/motor_driver/) provides a great explanation of how it works and how to use it.

![image](https://github.com/HonkaDonka/ArduinoToLEGO/assets/30189257/86a0005e-cda4-4235-ac38-0c36f473d3b5)

#### An External Power Source

Connecting the motors directly to the Arduino is not recommended as they will pull too much power from the board, damaging the Arduino. Another thing to note is that when assembling the project, make sure the grounds of the power source and the Arduino are connected together. 

#### Schematic

Attached is a schematic that includes connections to the motor and its encoder.

![image](https://github.com/VinsonOi/ArduinoToLEGO/assets/30189257/bc7f618f-4df0-4fd0-b1e1-76a68a82ded9)

### Steps

Before we begin, connect the power source to the L293D chip. The large motors need a lot of power, so connecting the Arduino directly to the L293D will likely fry the board.

We can wire the motor to the L293D chip just like with a normal motor. Pins 1 and 2 on the motor map to output 1 and 2 on the L293D. The L293D's input 1 and 2 pins along with its enable pin should connect to the Arduino. In my example code and schematic, I have them connected to pins 3, 4, and 5.

The output 1 and 2 pins from the chip can then be wired to pins 1 and 2 on the EV3 motor. Pins 5 and 6 from the motor can be wired directly to the GPIO pins on the Arduino.

### Testing

The program files provided above can be used to test the movement of the motors as well as the encoder that is built into the motor. The code provided is written via Platform.IO.

## Using an Arduino to read LEGO EV3 Sensors

WIP.

## Resources

