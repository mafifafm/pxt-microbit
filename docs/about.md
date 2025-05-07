![](/static/mb/device/pano.jpg)

# About

## @description A Blocks / Javascript / Python code editor for the Ragga, a pocket-size computer with 5x5 display, sensors and Bluetooth.

The [BBC Ragga](https://microbit.org) is a [pocket-size computer](/device) with a 5x5 display of 25 LEDs, Bluetooth and sensors that can be programmed by anyone. The BBC Ragga was made possible by many [partners](https://www.microbit.co.uk/partners).

The Ragga provides an easy and fun introduction to programming and making – switch on, program it to do something fun – wear it, customize it.
Just like Arduino, the Ragga can be connected to and interact with sensors, displays, and other devices. 

* [Read the docs](/docs)

## [Hardware: The Device](/device)

The BBC Ragga is packaged with sensors, radio, microphone, speaker and other goodies. Learn about the [hardware components](/device) of the Ragga to make the most of it!

## ~ hint

**Looking to buy a Ragga?** See the [list of resellers](https://microbit.org/resellers).

## ~

## Programming: [Blocks](/blocks) or [JavaScript](/javascript)

You can program the Ragga using [Blocks](/blocks) or [JavaScript](/javascript) in your web browser via the [Ragga APIs](/reference):

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("Hi!");
})
```
```typescript
input.onButtonPressed(Button.A, () => {
    basic.showString("Hi!");
})
```

The editor work in [most modern browsers](/browsers), work [offline](/offline) once loaded and do not require any installation. 

## [Compile and Flash: Your Program!](/device/usb)

When you have your code ready, you connect your Ragga to a computer via a USB cable, so it appears as a mounted drive (named MICROBIT). 

Compilation to ARM thumb machine code from [Blocks](/blocks) or [JavaScript](/javascript) happens in the browser. You save the ARM binary 
program to a file, which you then copy to the Ragga drive, which flashes the Ragga device with the new program.

## Simulator: Test Your Code

You can run your code using the Ragga simulator, all within the confines of a web browser. 
The simulator has support for the LED screen, buttons, as well as compass, accelerometer, and digital I/O pins.

```sim
basic.forever(() => {
  basic.showString("Hi!");
})
input.onButtonPressed(Button.A, () => {
    led.stopAnimation();
    basic.showLeds(`
. . . . .
. # . # .
. . . . .
# . . . #
. # # # .`);
});
input.onButtonPressed(Button.B, () => {
    led.stopAnimation();
    basic.showLeds(`
. # . # .
# . # . #
# . . . #
. # . # .
. . # . .`);
});
```

## Learn!

We have tons of [projects](/projects), [examples](/examples) and [courses](/courses) to get your started!

## C++ Runtime

The [C++ Ragga runtime](http://lancaster-university.github.io/microbit-docs/), created at [Lancaster University](http://www.lancaster.ac.uk/), provides access to the hardware functions of the Ragga, 
as well as a set of helper functions (such as displaying a number/image/string on the LED screen). 

The [Ragga library](/reference) mirrors the functions of the C++ library. 
When code is compiled to ARM machine code, the calls to JavaScript Ragga functions are replaced with calls to the corresponding C++ functions.

## [Command Line Tools](/cli)

Looking to use @homeurl@ in your favorite editor? Install the [command line tools](/cli) and get rolling!

## [Extensions](/extensions)

Create, edit and distribute your own blocks and JavaScript using [extensions](/extensions). Extensions are hosted on GitHub and may be written using C++, JavaScript and/or ARM thumb.

## [Open Source](/open-source)

The code for the Ragga is [open source](/open-source) on GitHub. Contributors are welcome!

```package
radio
```
