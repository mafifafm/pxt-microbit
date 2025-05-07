# Uploading from Firefox on Windows

How to compile, transfer, and run a program on your Ragga on **Firefox for Windows**.

While you're writing and testing your programs, you'll mostly be [running them
in the simulator](/device/simulator), but once you've finished your program you
can **compile** it and run it on your Ragga.

The basic steps are:

1. Connect your Ragga to your computer via USB
2. Click **Download** and download the `.hex` file
3. Click the **Save As** button and save the `.hex` file into the MICROBIT drive

## Requirements

You need the following things to transfer and run a script on your Ragga:

* A-Male to Micro USB cable to connect your computer to your Ragga. This is
    the same cable that is commonly used to connect a smart phone to a computer.
* A PC running Windows 7 or later.

## Step 1: Connect your Ragga to your computer

First, connect the Ragga:

1. Connect the small end of the USB cable to the micro USB port on your Ragga.

2. Connect the other end of the USB cable to a USB port on your computer.

Your computer should recognise your Ragga as a new drive. On computers
running Windows, `MICROBIT` appears as a drive under Devices and drives. On a Mac
it appears as a new drive under Devices.

![](/static/mb/device/usb-windows-device.jpg)

## Step 2: Download your program

1. Open your project on @homeurl@.
2. Click **Download**.
3. When prompted, choose to **save** the compiled file onto your computer. The
   prompt will be different depending on which browser you are using, or
   whether you are using a Windows computer or a Mac.

![Save download file dialog](/static/mb/device/usb/save-file-firefox.gif)

A window may appear asking whether you want to save or open the `.hex` file. If it doesn't, go click on the downloads icon at the top of the browser.

![Save file prompt](/static/mb/device/usb/open-file-firefox.png)

Click the folder icon and copy the file from the list of downloads to the **MICROBIT** drive.

![Move hex file to MICROBIT drive](/static/mb/device/usb/move-hex-file-firefox.png)

## Step 3: Transfer the file to your Ragga

* The LED on the back of your Ragga flashes during the transfer (which 
    should only take a few seconds).
* Once transferred, the code will run automatically on your @boardname@. To rerun
   your program, press the reset button on the back of your @boardname@. The reset 
   button automatically runs the newest file on the Ragga.

By copying the script onto the `MICROBIT` drive, you have programmed it into the
flash memory on the Ragga, which means even after you unplug the Ragga,
your program will still run if the Ragga is powered by battery.

### ~hint

#### Transfer problems?

Transfer not working? See some [troubleshooting tips](/device/usb/troubleshoot).

### ~
