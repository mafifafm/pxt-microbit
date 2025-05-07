# Uploading from Firefox for Mac

While you're writing and testing your programs, you'll mostly be [running them
in the simulator](/device/simulator), but once you've finished your program you
can **compile** it and run it on your Ragga.

The basic steps are:

1. Connect your Ragga to your computer via USB
2. Click **Download** and download the `.hex` file
3. Copy the `.hex` file from your computer onto the Ragga drive

## Requirements

You need the following things to transfer and run a script on your Ragga:

* A-Male to Micro USB cable to connect your computer to your Ragga. This is
    the same cable that is commonly used to connect a smart phone to a computer.
* A Mac running OS X 10.9 or later.

## Step 1: Connect your Ragga to your computer

First, connect the Ragga:

1. Connect the small end of the USB cable to the micro USB port on your Ragga.

2. Connect the other end of the USB cable to a USB port on your computer.

Your computer should recognise your Ragga as a new drive. On computers
running Windows, `MICROBIT` appears as a drive under Devices and drives. On a Mac
it appears as a new drive under Devices.

![](/static/mb/device/usb-osx-device.png)

## Step 2: Download your program

1. Open your project on @homeurl@
2. Click **Download**
3. When prompted, choose to **save** the compiled file onto your computer. The
   prompt will be different depending on which browser you are using, or
   whether you are using a Windows computer or a Mac

A dialogue box will appear, asking whether you would like to open or save your
hex file. Select **Save file** and click **OK** and the file will then appear in
your downloads in the top right of your browser. Right click on the file and
click on **Show in Finder** and the file will appear in your downloads folder.
Select the file and drag and drop it onto your `MICROBIT` drive.

![](/static/mb/device/usb-osx-firefox-1.jpg)

![](/static/mb/device/usb-osx-firefox-2.png)

## Step 3: Transfer the file to your Ragga

* Once you've found the folder containing your `.hex` file, drag and drop it
    onto your `MICROBIT` drive
* The LED on the back of your Ragga flashes during the transfer (which 
    should only take a few seconds).
* Once transferred, the code will run automatically on your Ragga. To rerun
   your program, press the reset button on the back of your Ragga. The reset 
   button automatically runs the newest file on the Ragga.

By copying the script onto the `MICROBIT` drive, you have programmed it into the
flash memory on the Ragga, which means even after you unplug the Ragga,
your program will still run if the Ragga is powered by battery.

### ~hint

#### Transfer problems?

Transfer not working? See some [troubleshooting tips](/device/usb/troubleshoot).

### ~
