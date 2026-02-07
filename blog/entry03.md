# Continue to tinker with Kaboom 
##### 2/2/26

### Where I am at Now
Throughout the Winter Break, I learned how to get an AI to move and attack with its own created bullet using components I learned in <a href="https://kaboomjs.com/">Kaboom.js</a>, which is a tool that me and my partner, Brianna will use to create our Spanish Platformer Game. I have already also learned how to create a platform that the player can jump on. My goal for tinkering with my tool going forward will be to figure out how to make the platform go from one side to another, being that the platform is only moving in one direction. 

### How I Created a One Direction Platform

















```js
player.onCollide("bullet", (bullet) => {
	destroy(bullet)
	destroy(player)
	addKaboom(bullet.pos)
})

```






[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
