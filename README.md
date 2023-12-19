# Chain-fabrosaurus
X-mas lights on my window

![buh](https://github.com/nicolasbaez/Chain-fabrosaurus/blob/main/xp022.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  h = w / 2;
  colorMode(HSB, h);
  clear();
  for (i = -h; i < h; i += 32)
    for (j = -h; j < h; j += 32) {
      push();
      stroke(abs(i), abs(j), h);
      noFill();
      translate(i, j, map(sin(i + w) + cos(j + w), -4, 12, -w, w));
      rotateY(w);
      rotateX(h);
      box(8, 8, 24);
      pop();
    }
  w -= 0.01;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp022.gif", 1024, { delay: 0, units: "frames" });
  }
};
