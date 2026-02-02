# Tinkering with My Tool

##### 12/15/25

### Where I am at Now
Throughout these few weeks, I am managing to understanding many components of <a href="https://kaboomjs.com/">Kaboom</a>, which is a tool that me and my partner, Brianna will use to create our Spanish Platformer Game. Being that we are individually tinkering with our tool, my goal for learning about Kaboom for winter break is to create interable platforms that the player can jump on. So far in my time, I learned how to create moving objects that go from one side to another that changes a scene if it collides with the character.


### How I Made my Base Starter for Creating Future Code
Keeping my goal in mind, I started out looking at Kaboom's website and seeing how each component is used in the code and change it as I take notes about my comprehension of the notes in my learning log. I first started with the <a href="https://kaboomjs.com/doc/intro">Introduction page</a>, following the steps to create a simple interactable jumping sandbox game where I have to jump over trees/rectangles, which I will get to later. At this point, one challenge that I had when creating the game downloading my own images into my game. When I downloaded my image and called it in `loadSprite`, the code wouldn't recognize it. I tried looking at Kaboom's website to see if I was doing anything wrong, but it looked like that I was doing everything correctly. After that, I asked Brianna if she knew what was the issue, turns out I had to code in `loadSprite("sprite", "sprites/sprite.png")` in order to give my sprite a name next to the path that unlocks the sprite for it to be accessible for `sprite()`. After this, I had to give them a variable name `player` and put their name given name in `loadsprite()` into the parathesis of `sprite()` from inside the variable's `add([})`. From there, I started editing with new components inside of `add([})` that determine a sprite's position and reactions when it comes in contact with another sprite. As well as the width and height of the ground the sprite will stand on.

```js

setGravity(2000) // defines gravity

const player = add([
    sprite("sprite"),  // renders as a sprite
    pos(120, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
    scale(0.2),      // determines size of sprite

])




add([
    rect(width(), 48),
    pos(0, height() - 48),
    outline(4), // gives sprite/floor an outline
    area(),
    body({ isStatic: true }), // isStatic = does not move
    color(127, 200, 255), // determines color of rectangle
])
```

Next, in order to make keys that move the sprite's position, I have to use `onKeyPress()` and `onKeyDown` to make the key buttons move the sprite in a certain direction. I would also have to put a variable for the speed at which the sprite's move by containing the variable inside of `.move()`. For making the sprite jump, it works the same as getting the other keys to move the sprite, except you do not need to make a seperate variable. You can just input the number at which height you would want the sprite to jump by using `.jump()`. To make the sprite only be able to jump once, I had to put `.isGrounded()` inside of a `if()` statement so that the sprite can only jump when it is on the ground. Along the way, I did also find a video that I will plan to watch later on about <a href="https://www.youtube.com/watch?v=TDqByrKVAZc">How to make wall jumps.</a>
```js

onKeyPress("space", () => {
   if (player.isGrounded()) { // code works if player is on a surface
 player.jump(800);
   }
})


onKeyDown("left", () => {
	// .move() is provided by pos() component, move by pixels per second
	player.move(-SPEED, 0)
})
const SPEED = 500

onKeyDown("right", () => {
	player.move(SPEED, 0)
})


const FLOOR_HEIGHT = 55;



add([
    rect(width(), 48),
    pos(0, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true }),
    color(127, 200, 255),
])
```

###### Full Base Starter
```js
kaboom() // starts the game

setGravity(2000) // defines gravity to sprites with a `body()`

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

onKeyPress("space", () => {
   if (player.isGrounded()) { // code works if player is on a surface
 player.jump(800);
   }
})


onKeyDown("left", () => {
	// .move() is provided by pos() component, move by pixels per second
	player.move(-SPEED, 0)
})
const SPEED = 500

onKeyDown("right", () => {
	player.move(SPEED, 0)
})


const FLOOR_HEIGHT = 55;



add([
    rect(width(), 48),
    pos(0, height() - 48),
    outline(4),
    area(),
    body({ isStatic: true }),
    color(127, 200, 255),
])
```




### How I Made Moving Rectangles

To make the trees, I had to use the same code that created the ground, except put it inside of a function so that the trees will spawn repeatly after a certain amount of time using `wait(rand())`. To make the trees move in a certain direction, I had to use `anchor()` to determine its position for where it moves and `botleft` to place it directly on the floor. To make the trees have an effect on the sprite, I had to use `onCollide()` so that when the player sprite collides with the tree, it changes to the losing screen, leaving the current score.

```js
function spawnTree() {

        // add tree obj
        add([
            rect(48, rand(32, 96)),
            area(),
            outline(4),
            pos(width(), height() - FLOOR_HEIGHT),
            anchor("botleft"),
            color(255, 180, 255),
            move(LEFT, SPEED),
            "tree",
        ]);

        // wait a random amount of time to spawn next tree
        wait(rand(0.5, 2.5), spawnTree);

    }

spawnTree();

    // lose if player collides with any game obj with tag "tree"
    player.onCollide("tree", () => {
        // go to "lose" scene and pass the score
        go("lose", score);
        burp();
        addKaboom(player.pos);
    });
```


### EDP
So far in the <strong>Engineering Design Process</strong>, I am between steps 2 and 3, which is to <strong>Research the Problem</strong> and **BrainStorm Possible Solutions**. I say this because I am currently researching the ways that I could use Kaboom to make our Freedom Project by looking through videos to not see how to make a full game, but to see how each component is used. This way, I brainstorm possible ways that Kaboom can be used when me and my partner create the project. I already found one video that explains <a href="https://www.youtube.com/watch?v=iM1iSvloMlo">how to make an AI boss and shift from different scenes</a>.

### Skills Learned
I feel like I am growing in **Perservance** because learning all the concepts that I reviewed so far were difficult to understand at first. I am still trying to understanding how to create different scenes using Kaboom.js. But as I took my time, trying to explain the code I am seeing in my learning log, it became a lot easier. Another skill that I am improving in but still working on is **Problem Decomposition**. I say this because espcially with using `add(){}` many components, there can be a lot of code that looks like a lot to break down just by trying to do one simple thing. For instance, I am still trying to implement the score onto my game because when I try using it, the whole game does not work at all. So applying this skill has definitely helped me in not just understanding the code, but also helping me find the time to do it.


### Next Steps
Throughout these next few weeks, I am planning on also making an AI sprite that attacks the player, but before I do that, I am trying to make a platform that moes back anf forward so that I can first understand how to get the AI sprite to move on its own. Overall, I do enjoy learning about Kaboom and its components and I am eager to learn more about it!

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
