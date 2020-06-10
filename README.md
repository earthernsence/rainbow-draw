# rainbow-draw
i made a rainbow draw

![image](https://user-images.githubusercontent.com/35183947/84321438-c5024500-ab38-11ea-877e-c077326faab4.png)

To change the color:
go to line 39 of script.js:
```js
ctx.strokeStyle = `hsl(${hue}, 100%, 50%)`;
```
We already defined `hue` at the top, in my variables section. It starts at 0 but goes up per draw event (each time the mouse is down).
You can make the `hue` go up by less by changing `hue++;` to something like `hue += 0.5` to make the hue increase half as fast.
That 0.5 number can be any number you want.
In the `hsl()` block, you can change the saturation (the middle number) and the lightness (the last number). They are always percents.

To change the width of the brush:
Start at line 33 of script.js:
```js
ctx.lineWidth = 100;
```
Here, you can literally just change the line width starting number. Anything equivalent 100 or 1, and anything greater than 100 and less than 1 will immediately go back down within 1 and 100. So how do you change that?
Take a look at line 54.
```js
    if (ctx.lineWidth >= 100 || ctx.lineWidth <= 1) direction = !direction;

    if (direction) {
        ctx.lineWidth++;
    } else {
        ctx.lineWidth--;
    }
}
```
`direction` is already defined in my variables as true, which means it is increasing. Why? Because that `if (direction)` (which is saying if direction is true) tells it to because directions is true so it will increase the line width. If you want to remove line width changing entirely, remove the direction variable and line 54 down. But, if you want to make it increase faster, take what you saw in the `hue` bit: turn `ctx.lineWidth++;` into `ctx.lineWidth += 2`. Again, that 2 can be anything. This way, you can make it increase faster or slower. But take a look at 54 again: if it's above 100 or below 1 it will inverse it and make it go down. These numbers are your upper and lower bounds: changing 100 into 500 will make it go to 500 and then back down to 1. Changing that 1 will change how far down you want it to go. Setting this to 0.1 means it will go all the way down to 0.1 and then back up. To make that work properly, though, you will probably have to edit the changing of the number in line 56 on. 

I hope this is comprehensive enough. If you have any issues leave them in the issues tab of this repo.
