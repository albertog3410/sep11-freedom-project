# Tinkering with My Tool

##### 12/15/25

### Where I am at Now
So far in my SEP11 Freedom Project, I had just begun to tinker with my tool <a href="https://kaboomjs.com/">Kaboom</a>, which is a tool that me and my partner, Brianna will use to create our Spanish Platformer Game. Being that we are individually tinkering with our tool, my goal for learning about Kaboom for winter break is to create interable platforms that the player can jump on. So far in my time, I learned how to create moving objects that go from one side to another that changes a scene if it collides with the character. The code that I used for this was `.onCollide`, and many new aspects of using `add([])`.  


### How I tinkered with Kaboom
Keeping my goal in mind, I started out looking at Kaboom's website and seeing how each component is used in the code and change it as I take notes about my comprehension of the notes in my learning log. 


create a simple interactable jumping sandbox game



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

### Challenges I had with Kaboom
 One challenge that I had when tinkering with Kaboom was how I can download my own images into my game. When I downloaded my image and called it in `loadSprite`, the code wouldn't recognize it. I tried looking at Kaboom's website to see if I was doing anything wrong, but it looked like that I was doing everything correctly. After that, I asked Brianna if she knew what was the issue, turns out I had to code in `loadSprite("sprite", "sprites/sprite.png")` in order to give my sprite a name next to the path that unlocks the sprite in `loadSprite`. 
 
















[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
