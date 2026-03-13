# Working Towards MVP
##### 3/10/26

### Where I am at Now 
Throughout these weeks, me and my partner Brianna are planning on moving towards creating our Freedom Project Spanish Platformer Game. Before we start to create our project, we first had to plan out what we were going to do by making an **MVP(Minimum Viable Product)**. This means planning on creating something small using what learned on <a href="https://kaboomjs.com/">kaboom.js</a> that can be used to form our game. My goal was to create a health bar for my character and make it so whenever my player is attacked by the AI that I created. After doing that, I would have to link up the player's health bar to a series of prompts that Brianna would create. While this task still is not finished yet, I will show below how much I have managed to do to build towards the MVP. 

### How I Attempted to make Player Healthbar and How it Went Wrong

To start off, I used a component known as `health()`, which gives a sprite a certain amount of health and added it to my character. However, being that the health of the player does not show on the screen, I created a variable named `pHealth` that has the same number as the player's health and put that number as text. Then using Brianna's randomized prompts, I used `if()` statements to specify that if the user gets a question wrong, the player's health and the `pHealth()` number decreases as well. Finally, I stated that if the `pHealth()` number reaches 0, it takes away the player sprite from the screen. 

```js
var pHealth = 3;

add([
text("Points:" + " " + pHealth + "      " +  "Press F to answer questions and earn points"),
])

const player = add([
    sprite("sprite"),  // renders as a sprite
    pos(80, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
    scale(0.2),
    health(3),
])



onKeyPress("space", () => {
   if (player.isGrounded()) {
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
onKeyDown("up", () => {
	player.move(0, -SPEED)
})

onKeyDown("down", () => {
	player.move(0, SPEED)
})




var foodQuest = ["What is the most popular food in the world?", "what fruit is claimed to be a berry but ultimately isn't?", "What food is commonly eaten in Japan?"];



onKeyPress("f", () => {
var randomQuest = Math.floor(Math.random() * (3));
if (randomQuest == 0) {
  var ansZero = prompt(foodQuest[0]);
    if (ansZero === "rice" || ansZero === "Rice") {
        alert("That's Correct!");
       pHealth += 1;
    } else {
        alert(ansZero + " is not the correct answer.. Sorry!");
        pHealth -= 1;
    }


}

else if (randomQuest == 1) {
    var ansOne = prompt(foodQuest[1]);
      if (ansOne === "strawberry" || ansOne === "Strawberry") {
          alert("That's Correct!");
       pHealth += 1;
      } else {
          alert(ansOne + " is not the correct answer.. Sorry!");
        pHealth -= 1;
      }
}


    var ansTwo = prompt(foodQuest[2]);
      if (ansTwo === "ramen" || ansTwo === "Ramen") {
         alert("That's Correct!");
       pHealth = pHealth + 1;
      } else {
        alert(ansTwo + " is not the correct answer.. Sorry!");
        pHealth = pHealth--;
      }


})
```

However, when I ran the code, answering the prompt right or wrong did not change the `pHealth` number. I tried to debug the code to the best of my ability, some things I did was changing the `pHealth` inside the else statements into a different form of adding and subtracting one. For instance, instead of doing `pHealth++`, I tried doing `pHealth = pHealth + 1` in order to say that instead add one every time, have pHealth equal what the number originally was by one. Even with this, the same results showed. 





### EDP
So far in the Engineering Design Process, I am at step 5, which is to **Create A Prototype**. I say this because in order to understand what we were going to do first when creating the game, me and Brianna had to first create an MVP in order to break our project down into smaller pieces. This way, we can effectively plan out how we were going to set up our project.  

### Skills 
I feel like I am growing in 


### Next Steps


What I plan on doing is telling Brianna about the issue that I am having, this way we can both figure out a solution to what is happening with the code. 

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
