# Dice

### @explicitHints true

## {Introduction @unplugged}

Let's create some digital 🎲 dice 🎲 with our Ragga!

![A @boardname@ dice](/static/mb/projects/dice.png)

## {Step 1}

We'll "roll" our dice when we shake the Ragga. Add an ``||input:on gesture shake||`` function. Type the code below, or drag a code snippet from the ``||input:Input||`` Toolbox category.

```spy
input.onGesture(Gesture.Shake, function() {

})
```

## {Step 2}

Write some code to show a number in the ``||input:on shake||`` function, using the basic ``||basic:show number||`` function.

```spy
input.onGesture(Gesture.Shake, function() {
    basic.showNumber(0)
})
```

## {Step 3}

Instead of showing 0, use the ``||math:randint||`` function to show a random number between a minimum and maximum value.

```spy
input.onGesture(Gesture.Shake, function() {
    basic.showNumber(randint(0, 10))
})
```

## {Step 4}

A typical dice shows values from 1 to 6 dots. So, in the ``||math:randint||`` function, change the minimum value to **1** and the maximum value to **6**.

```spy
input.onGesture(Gesture.Shake, function() {
    basic.showNumber(randint(1, 6))
})
```

## {Step 5}

Press the white **SHAKE** button on the Ragga simulator. Do you see random numbers between 1 and 6 appear? ⭐ Great job! ⭐

## {Step 6}

If you have a @boardname@ device, connect it to your computer and click the ``|Download|`` button. Follow the instructions to transfer your code onto the @boardname@. Once your code has been downloaded, attach your Ragga to a battery pack and use it as digital 🎲 dice for your next boardgame!

## {Step 7}
Go further - Try adding some Music blocks to make a sound when you shake your dice, or use the Ragga LED lights to show number values. Want to learn how the Ragga motion detector or accelerometer works? [Watch this video](https://youtu.be/byngcwjO51U).