# Continue to tinker with Kaboom 
##### 2/2/26

### Where I am at Now
Throughout the Winter Break, I learned how to get an AI to move and attack with its own created bullet using components I learned in <a href="https://kaboomjs.com/">Kaboom.js</a>, which is a tool that me and my partner, Brianna will use to create our Spanish Platformer Game. To make the AI attack and move, I used components such as `state()`, and `.onStateEnter()` to make the AI change from moving to attacking.  I have already also learned how to create a platform that the player can jump on. My goal for tinkering with my tool going forward will be to figure out how to make the platform go from one side to another, being that the platform is only moving in one direction. 

### How I Created a One Direction Platform
I created the platform by first making my own sprite and implementing an online image using `loadSprite()` and then containing it inside of its own variable and putting the `body()` as `isStatic`. This way, the platform will not automatically fall to the ground and stay in the air. To make it move, I used the `move()` component to make it go left and right, but also still an interable element. However, an issue that I ran into and still am working on fixing is that the platform only moves in whichever direction is shown first in the variable, in this case it is the left direction. 

```js
const platform = add([
    sprite("platform"),
    pos(200, 400),
    area(),
    scale(0.3),
  body({ isStatic: true }),
        move(LEFT, 40),
        move(RIGHT, 40),

])

```
### How I Created an AI Enemy 
After first creating the enemy character inside a variable, I used a new component called `state()` that is meant to tell the AI what actions it can take in what order using the <a href="https://kaboomjs.com/#state">Kaboom.js library</a>. The actions that the enemy AI can take are arranged to having it moving to then attacking with it stopping for a short period of time, `state("move", [ "idle", "attack", "move" ])`. Then using `.onStateEnter()`, I make the enemy AI switch to another state after a certain period of time using `await`. 


```js
enemy.onStateEnter("idle", async () => {
	await wait(0.5)
	enemy.enterState("attack")
})


await wait(1)
	enemy.enterState("move")

})

enemy.onStateEnter("move", async () => {
	await wait(2)
	enemy.enterState("idle")
})


```
Lastly, I had to make a bullet that the enemy AI can fire to attack the player. To do this, I had to make the bullet itself in an individual `add()` element while applying two seperate variables containing its bullet and enemy speed for when the bullet collides with the player. 
```js
		add([
			pos(enemy.pos),
			move(dir, BULLET_SPEED),
			rect(12, 12),
			area(),
			offscreen({ destroy: true }),
			anchor("center"),
			color(BLUE),
			"bullet",
		])

	}
player.onCollide("bullet", (bullet) => {
	destroy(bullet)
	destroy(player)
	addKaboom(bullet.pos)
})

```



### Engineering Design Process 
So far 





[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
