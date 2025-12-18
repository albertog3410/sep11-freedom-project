# Tinkering with My Tool

##### 12/15/25


### Where I am at Now
So far in my SEP11 Freedom Project, I had just begun to tinker with my tool <a href="https://kaboomjs.com/">Kaboom</a>, which is a tool that me and my partner, Brianna will use to create our Spanish Platformer Game. 







### How I tinkered with Kaboom
Since we have decided to go tinker with Kaboom, I decided to go with the same task I had for when I was trying to tinker with Phaser, due to the time I had left, my goal for this tool was to create an interable environment using the code I learned. After installing Kaboom, I was mainly looking at its website to see how I can download my own images into my game. However, when I downloaded the image and called it in `loadSprite`, the code wouldn't recognize it. I asked Brianna if she knew what was the issue, turns out I had to give to give my sprite a name next to the path that unlocks the sprite in `loadSprite`. Along the way, I also learned about other codes that I used to create a short sandbox where you can just repeatly jump, similar to a flappy birds game.  

```js
// start the game
kaboom()

// define gravity
setGravity(2000)

// load a default sprite
loadSprite("sprite", "sprites/sprite.png")


// add character to screen, from a list of components
const player = add([
    sprite("sprite"),  // renders as a sprite
    pos(120, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
    scale(0.2),     // size of the sprite

])
```









[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
