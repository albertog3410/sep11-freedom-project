# Deciding on What to do for Project and Tools
##### 11/3/2025

### Where I am at Now
For my SEP11 Freedom Project, I am working with a classmate, Brianna, in order to create a Spanish Learner Platform Game. Before choosing to work with a partner on this project, I had an idea to make a platformer game that involved answering a trivia and based on how many questions you get right from the trivia, the rewards you get from the correct answers would help you advance in the game. Thats when I noticed that Brianna had a similar idea, where her idea was to have an education platformer game where it helps you learn spanish. So, we decided to combine our ideas together and both work on the freedom project.

### How we Choose Our Tool and How I Planned to Tinkered with My Tool
Orginally, I thought of using <a href="https://phaser.io/tutorials/getting-started-with-phaser-launcher"> Phaser</a> for my project, however Brianna also wanted to use <a href="https://kaboomjs.com/"> Kaboom</a>. Due to this, we agreed that we would seperately work on the tools we have orginally chosen. My goal for tinkering with Phaser was to create a short mini game using what I have taken notes on in my <strong>Learning.Log</strong>. I eventually found a <a href="https://github.com//phaserjs/editor-scripts-quick"> Github Phaser Editor Page</a> that contained pieces of code from the Phaser Editor that I could use that also gives a brief explanation of what the code does. which made it harder to me to start using the tool in my IDE. However, I was not able to fully tinker with these Phaser components because of the lack of time I had. I was also struggling with downloading Phaser into my IDE, which made it more difficult for me to get started with tinkering with my tool. 

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
    scale(0.2),

])
```


### EDP 
I am currently in Step 2 of the Engineering Design Process, which is to <strong>Research the Problem</strong>. I say this step because in order for me and my partner to be able to create our project, we would first have to understand what tool we are both going to use. Being that we decided to go with Kaboom, Brianna says that she knows some seniors that have also used Kaboom that could help us with understanding how to use this tool. 


### Skills I have Learned and Final Thoughts 
 From this experience, I learned that for the future of this project that some skills I should work on are:
* <strong> Time Management </strong>. I say this because despite not having the time to actually use Phaser myself, I still do feel like that there was more that I could of done with the time that I had. I would often focus more on my school work that I would forget about tinkering with Phaser.
* <strong>Organization</strong> - When I started with my original tool and Kaboom, my notes were not organized in a way that shows me how I could understand how to use the code for myself. Now, I'm working towards explaining my code in a way that I can better understand it.
* <strong>Asking for Help when Needed</strong> - Often times, I had to ask for help about certain code to Brianna when I started to tinker with Kaboom. Keeping this in mind, I do feel better now that I will not be alone in learning a new tool this time.

Overall, despite the lack of time I had, I am enjoying tinkering with Kaboom and I am interested in learning about all its components so that I may use to create my Freedom Project Game!





[Next](entry02.md)

[Home](../README.md)
