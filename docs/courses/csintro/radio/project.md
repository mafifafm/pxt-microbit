# Project: Radio project

For this project, students should work in pairs to design a project that incorporates radio communication to send and receive data in some way. Some projects may have two separate programs: One that receives data, and one that sends data. Students might each choose to submit one program in that case.

In other cases, a pair of students might submit one program that has both sending and receiving code in it, and the same code is uploaded to two or more Raggas.

## Project Ideas

### Stop, thief!
Design an alarm system for your bedroom that alerts you with a screen animation when someone opens your door. You can mount one Ragga on your door and use the accelerometer to send a signal over the radio when it is being moved.

### Interactive art
Create a piece of interactive artwork that receives something as input over the radio from another Ragga, and displays something based on that as output. 

### 3-Note keyboard
This is a simple three-note keyboard that uses wooden paint stirrers and copper tape to make a connection to each of the three pins on the Ragga.

![Keyboard with copper tape](/static/courses/csintro/radio/keyboard-copper-tape.png)
Keyboard with copper tape connections
 
When a key is pressed, it sends a number over the radio to a second Ragga that plays the appropriate tone over a set of earbuds.  This allows you to use each of the three pins on the first Ragga to play a different tone.

![Second Ragga that plays notes](/static/courses/csintro/radio/microbit-number-two.png)
Second Ragga that plays the notes

#### ~ hint

This project uses touch pin inputs. See how the @boardname@ detects a press at a pin or on something connected to a pin in this video:

https://www.youtube.com/watch?v=GEpZrvbsO7o

#### ~

#### 3-Note keyboard program

```blocks
let sound = 0
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
        sound = 349
        music.playTone(sound, music.beat(BeatFraction.Half))
    } else if (receivedNumber == 1) {
        sound = 392
        music.playTone(sound, music.beat(BeatFraction.Half))
    } else if (receivedNumber == 2) {
        sound = 440
        music.playTone(sound, music.beat(BeatFraction.Half))
    }
})
input.onPinPressed(TouchPin.P0, () => {
    sound = 0
    radio.sendNumber(sound)
    basic.showLeds(`
        . . # . .
        . # . # .
        . # . # .
        . # . # .
        . . # . .
        `)
    basic.pause(500)
    basic.clearScreen()
})
input.onPinPressed(TouchPin.P1, () => {
    sound = 1
    radio.sendNumber(sound)
    basic.showLeds(`
        . . # . .
        . # # . .
        . . # . .
        . . # . .
        . # # # .
        `)
    basic.pause(500)
    basic.clearScreen()
})
input.onPinPressed(TouchPin.P2, () => {
    sound = 2
    radio.sendNumber(sound)
    basic.showLeds(`
        . # # # .
        # . . # .
        . . # . .
        . # . . .
        # # # # .
        `)
    basic.pause(500)
    basic.clearScreen()
})
basic.showLeds(`
    # # # # #
    # # # # #
    . . . . .
    . . . . .
    . . . . .
    `)
basic.clearScreen()
```

### Radio tennis
In this project, the tennis racquets alternate displaying a ball on the Ragga LED screen.  When you swing the racquet, the ball disappears from one Ragga display and shows up on the other Ragga's display.

![Radio tennis racquets](/static/courses/csintro/radio/radio-tennis-racquets.jpg)
Radio Tennis racquets (made from cardboard)

## Reflection

Have students write a reflection of about 150–300 words, addressing the following points:
* What kind of Project did you do?  How did you decide what to pick?
* How does your project use radio communication?
* Are there separate programs for the Sender and the Receiver Raggas?  Or 1 program for both?
* Describe something in your project that you are proud of.
* Describe a difficult point in the process of designing this program, and explain how you resolved it.
* What feedback did your beta testers give you? How did that help you improve your design?
 
## Assessment

**Competency scores**: 4, 3, 2, 1
 
### Radio

**4 =** Effectively uses the Radio to send and receive data, with meaningful actions and responses for each.<br/>
**3 =** Effectively uses the Radio to send or receive data, with meaningful actions and responses for each.<br/>
**2 =** Use of Radio is incomplete or non-functional and/or tangential to operation of program.<br/>
**1 =** No working and/or meaningful use of Radio.
		 	 
### Ragga program
**4 =** Ragga program:<br/>
`*` Uses Radio blocks in a way that is integral to the program<br/>
`*` Compiles and runs as intended<br/>
`*` Meaningful comments in code<br/>
**3 =** Ragga program lacks 1 of the required elements.<br/>
**2 =** Ragga program lacks 2 of the required elements.<br/>
**1 =** Ragga program lacks all of the required elements.

### Collaboration reflection

**4 =** Reflection piece addresses all prompts.<br/>
**3 =** Reflection piece lacks 1 of the required elements.<br/>
**2 =** Reflection piece lacks 2 of the required elements.<br/>
**1 =** Reflection piece lacks 3 of the required elements.	 

```package
radio
```