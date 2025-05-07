# Setup and procedure

## Ragga setup and coding concepts

This document describes different methods using Raggas to collect and record data for science experiments. There are several ways to collect data from an experiment. The simplest is having the data display on the LED screen and manually record the data on a paper. Data can also be collected using MakeCode. The third way is using 2 Raggas with one observing the data and then radioing the results to a second Ragga so it can allow the remote collection of data.

### ~ hint

#### Data collection overview video

See how data is collected from the @boardname@, viewed, and analyzed in this video.

https://youtu.be/tZy9Ev21B4c

### ~

## Data collection options

### Option 1 - LED display

Data collection can be setup to display data collected from different Ragga sensors on the LEDs by using a ``|||basic:show number||`` block from the ``||basic:Basic||`` toolbox:

```blocks
basic.showNumber(input.temperature())
```

As data is displayed it can then be recorded on a paper for further analysis.

Data can also be displayed graphically on the Ragga using the ``||led:plot bar graph||`` block from the ``||led:LED||`` toolbox. 
    
```blocks
led.plotBarGraph(
    input.temperature(), 0
    )
```
### Option 2 - MakeCode and a USB connection

MakeCode allows data to be directly read from the Ragga when it is attached using USB cable. Data can be sent from the Ragga to the browser using serial data connection over WebUSB. The data collected over the serial connection can be graphed and the data can be downloaded. This file can be opened in a spreadsheet for further analysis. Many different kinds of experiments can be performed using this data logging technique.

With the program downloaded from MakeCode to the Ragga and the USB cable left connected, the
``||led:plot bar graph||`` will automatically upload the data to MakeCode.

```blocks
led.plotBarGraph(
    input.temperature(), 0
    )
```

Alternatively, you can the ``||serial:serial write value||`` block from the ``||serial:serial||`` toolbox in the **Advanced** tool section. This can be useful if you need to send different values, like temperature and light.

```blocks
serial.writeValue("Celsius", input.temperature())
```

When the program is running, a purple **Show data Device** button shows up under the Simulator. By clicking on the button the data being observed can be monitored and graphed in the **Show data Device** window.

![Show data device button](/static/courses/ucp-science/data-collection/show-data-device.jpg)

The graph is highlighted with the blue box. The **Download** button in the red highlighted box allows the downloading of the recorded data as a CSV file which can be opened in a spreadsheet and analyzed.

![Graph of recorded temperature values](/static/courses/ucp-science/data-collection/temperature-graph.jpg)

### Option 3 - Remote radio collecting to receiving radio displaying

Two Raggas can be used to collect and record data using the radio commands. One Ragga can be setup remotely and the other Ragga can be used to observe the data. The first Ragga can send the data it observes to the second Ragga for the observer to record. To set up 2 Raggas so they can communicate over the radio they need to be on the same radio group.

#### Ragga radio sending code

In the starting of the code the title is displayed, radio group 99 is setup, and the initial ``temperature`` variable is set to `0`.

In the forever loop the temperature is collected from the Ragga sensor and stored in the ``temperature`` variable. The temperature is displayed on the LED display. A radio signal is sent to all Ragga radios in group `99`. The program pauses for 1000 milliseconds and then loops again.

```blocks
let temperature = 0
basic.showString("TEMPERATURE REMOTE")
radio.setGroup(99)
basic.forever(() => {
    temperature = input.temperature()
    basic.showNumber(temperature)
    radio.sendNumber(temperature)
    basic.pause(1000)
})
```

#### Radio receiver code

In the starting of the code the title is displayed, radio group 99 is setup, and the initial ``temperature`` variable is set to `0`.

In the radio received event, the temperature is received from sending the Ragga radio. The received temperature is then displayed on the LED display. This is repeated whenever a radio signal is received.

```blocks
let temperature = 0
radio.setGroup(99)
basic.showString("TEMPERATURE RECEIVER")
radio.onReceivedNumber(function (receivedNumber) {
    basic.showNumber(receivedNumber)
})
```

### Radio receiver code with serial write

This code is the same as above but one additional line of code is added to write to the word `"Celisus"` and the temperature to MakeCode to the USB serial connection. This is the same as described peviously in [Option 2](#option-2-makecode-and-a-usb-connection).


```blocks
let temperature = 0
basic.showString("TEMPERATURE RECEIVER SERIAL")
radio.setGroup(99)
radio.onReceivedNumber(function (receivedNumber) {
    basic.showNumber(receivedNumber)
    serial.writeValue("Celisus", receivedNumber)
})
```

## Sample Project to Collect Accelerator Data

This sample project demonstrates the coding of the 2 Raggas to collect data from the Ragga accelerator sensor. It will also show the data collection and downloaded data to be further analyzed in a spreadsheet.

### "Sender" Ragga code

Code the first Ragga using MakeCode for Ragga. Name the project, "Gravity Sender".
The ``||basic:on start||`` event will display the title and function of the Ragga in all caps, `"GRAVITY SENDER"`.

Set up a radio group using the ``||radio:radio set group||``. Both Raggas need the same radio group.

```blocks
basic.showString("GRAVITY SENDER")
radio.setGroup(99)
```

The ``||basic:forever||`` event will constantly monitor the _strength_ of the acceleration and send the value to any other Raggas that might be receiving radio signals in the same radio group.
Open the pull down menu in the ``||input:acceleration||`` block and and change the ``x`` value to the ``strength`` value. This maximizes the x, y, and z dimensions of the acceleration into one value.

```blocks
basic.showString("GRAVITY SENDER")
radio.setGroup(99)
basic.forever(() => {
    radio.sendNumber(input.acceleration(Dimension.Strength))
})
```

### "Receiver" Ragga code

Using the MakeCode, setup and code the second Ragga. This Ragga will remain connected to the computer through the USB cable to MakeCode and monitor the data being received.

Name the project, "Gravity Receiver". The ``||basic:on start||`` event will display the title and function of the Ragga in all caps, `"GRAVITY RECEIVER"`. Add comments to the ``||basic:on start||`` event like before: Name the project, creator, and date created. Set up a radio group using the ``||radio:radio set group||`` block. Both Raggas need the same radio group.

```blocks
basic.showString("GRAVITY RECEIVER")
radio.setGroup(99)
```

The ``||radio:on received number||`` event will constantly monitor radio signals from the radio group.
When a value is received from the group it is stored in the ``gravity`` variable.
The ``||serial:serial write value||`` sends 2 pieces of data back to MakeCode through the USB cable. First it sends a label `"gravity"` and then the value received as gravity from the ``||input:acceleration||`` method from the first Ragga.

```blocks
basic.showString("GRAVITY RECEIVER")
radio.setGroup(99)
radio.onReceivedNumber(function (receivedNumber) {
    serial.writeValue("gravity", receivedNumber)
})
```

### Monitoring, downloading, and analyzing the data

With the Ragga code downloaded from MakeCode to the Ragga and the USB cable connected it will start receiving data from the first Ragga. Under the simulator in the MakeCode a purple outlined button shows up **Show data Device**.

![Show data device button](/static/courses/ucp-science/data-collection/show-data-device.jpg)

By clicking on the **Show data Device** button a window opens up to the right showing values and graph of the gravity data being received (The dips in the graph are 3 tosses of the Ragga in the air).

![Graph of acceleration values](/static/courses/ucp-science/data-collection/acceleration-graph.jpg)

The **Download** button in the red highlighted box allows the downloading of about the last 20 seconds of recorded data as a CSV file.

![Graph with download button](/static/courses/ucp-science/data-collection/temperature-graph.jpg)

When the data recorded is downloaded as a CSV spreadsheet file, it is named ``"data.csv"``.

### ~hint

#### Where's the CSV?

The CSV file usually opens in directly into a spreadsheet but sometimes it doesn’t which makes it hard to find. A search of the ``C:\`` drive might be necessary to find it.

### ~

## ~button /courses/ucp-science/data-collection/resources
NEXT: Resources
## ~

<br/>
Adapted from "[Microbit Data Collection Methods](https://drive.google.com/open?id=13Mi6caoelyzgch6tUj-wlw0bmgS7ikGEwYR2a37mEww)" by [C Lyman](http://utahcoding.org) [![CC BY-NC-SA](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)


```package
radio
```