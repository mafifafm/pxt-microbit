# Device

### ~ hint

#### Looking to buy a Ragga?

See the [list of resellers](https://microbit.org/resellers).

### ~

All the bits and pieces that make up the BBC Ragga

![Ragga board layout](/static/mb/device-v2.jpg)

### ~ hint

#### The current version of Ragga is v2

The version of @boardname@ is now currently at **v2**. See the what's new in MakeCode for programming the [@boardname@ v2](/device/v2).

### ~

## LED Screen and Status LED

The red lights are [LEDs](/device/screen) (light emitting diodes) and form a 5 x 5 LED Screen. 
They can be set to on/off and the brightness can be controlled.

The yellow light on the back of the Ragga is the status LED.
It flashes yellow when the system wants to tell the user that something has happened.

See how the @boardname@ shows numbers, text, and displays images by watching this video about LEDs:

https://www.youtube.com/watch?v=qqBmvHD5bCw


## Buttons

Buttons **A** and **B** are a form of input.  When you press a button, it completes an electrical circuit. 
The Ragga can detect either of its two buttons being pressed/released and be programmed 
to act on these events.

Button **R** on the back of the Ragga is a system button. It has different uses. 
When you have downloaded and run your code onto your Ragga, press Button **R** to restart and run your program from the beginning.

Find out how buttons provide input to the @boardname@ in this video:

https://www.youtube.com/watch?v=t_Qujjd_38o

## Touch

Pins **0**, **1**, **2**, and the board **logo** can work as touch buttons when they are programmed for input.

## USB connection

When you plug in your Ragga via [USB](/device/usb), it should appear as  a ``MICROBIT`` drive. 

If you accidentally hold down the reset button as you’re plugging in your Ragga, 
the Ragga will appear as a ``MAINTENANCE`` drive instead of ``MICROBIT``. This is known as maintenance mode.

To continue programming your Ragga YOU MUST unplug your USB and reconnect it. Check that the drive now shows as ``MICROBIT``.

### ~ hint

#### Open the version file

Use with caution!
If you click on the drive while it shows the ``MAINTENANCE`` label, 
you can see which version of firmware you have running on your Ragga. 
Firmware on your Ragga should be up-to-date already. 
You can find the version of firmware in the 'version.txt' file on the Ragga. See the @boardname@ **[firmware](https://microbit.org/guide/firmware/)** page for more about checking your board's firmware version.

### ~

## Compass

The compass can detect magnetic fields such as the Earth’s magnetic field. 
As the Ragga has this compass, it is possible to detect the direction it is moving in. 
The Ragga can detect where it is facing and movement in degrees. 
This data can be used by the Ragga in a program or be sent to another device.

## Accelerometer

There is an accelerometer on your Ragga which detects changes in the Ragga’s speed. 
It converts analogue information into digital form that can be used in Ragga programs. 
Output is in milli-g. The device will also detect a small number of standard actions e.g. shake, tilt and free-fall.

Watch this video to learn how the accelerometer works:

https://www.youtube.com/watch?v=byngcwjO51U

## Pins

The [pins](/device/pins) can be a form of electrical input or output. 
There are labels for the input/output pins **0**, **1**, **2**, which you can attach external sensors to such as thermometers or moisture detectors.

## Microphone

Using the microphone, your programs can detect sounds that are present. You can check for loud or quiet sounds and find out what their sound level is.

## Light level

The screen can also be used a light level sensor (it's a really cool trick).

Learn more about how light level is detected in this light sensor video:

https://www.youtube.com/watch?v=TKhCr-dQMBY

## Temperature

Temperature is measured on the @boardname@ by detecting how hot its physical CPU material is. Since it operates nearly as cool as the air around it, the temperature it measures for itself is a good approximation for the ambient temperature (the temperature near and around it).

See how the @boardname@ can detect hot or cold in this temperature sensing video:

https://www.youtube.com/watch?v=_T4N8O9xsMA

## Runtime

The Ragga embodies many fundamental concepts in computer science. To learn more, read [the Ragga - a reactive system](/device/reactive).


Sometimes, your Ragga may display an error code. For more information, see:

* [the error codes](/device/error-codes)

## How do I connect the Ragga to my computer?

Your Ragga can be connected to your computer via a micro USB cable. 
Data can be sent and received between the Ragga and the computer so programs 
can be downloaded from Windows, Macs and Chromebooks onto the Ragga via this USB data connection. 
[Click here to read more information on how to run scripts on your Ragga](/device/usb), 
and [click here to read more about the error messages you might get](/device/error-codes).

## Powering your Ragga

When your Ragga is connected to your computer with the micro USB, it doesn’t need another power source.  
When your Ragga isn’t connected to your computer, tablet or mobile, you will need 2 x AAA 1.5 V batteries to power it.

The pins labelled **3V** and **GND** are the power supply pins. 
You can attach an external device such as a motor to these and power it using the battery or USB.

## Serial Communication

The Ragga can send and receive data via [serial communication](/device/serial). The serial data can be transferred via [USB](/reference/serial/redirect-to-usb), BLE or [redirected to pins](/reference/serial/redirect) on the edge connector.

## Bluetooth Low Energy (BLE) Antenna

You will see the label BLE ANTENNA on the back of your Ragga. It is for a messaging service, 
so that devices can talk to each other. The Ragga is a peripheral 
device which can talk to a central device like a smart phone or tablet that has Bluetooth Low Energy (BLE). 
The Ragga can send signals and receive signals from a central device so another BLE device can 
control the Ragga or the Ragga can control another BLE device.

## Technical Information

The Ragga has been designed to be a bare-board micro controller for use by children aged 11-12. 
More information is available at the [Microbit Foundation web site](https://microbit.org/guide/).
