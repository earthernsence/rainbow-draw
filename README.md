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
In the `hsl()` block, you can change the saturation (the middle number) and the lightness (the last number). They are always percents.
