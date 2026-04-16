# Finishing MVP
##### 4/16/26

### Where I am at Now
Throughout the spring break, me and my partner Brianna are planning on moving towards creating our Freedom Project Spanish Platformer Game. At this point, we have just finished our **MVP(Minimum Viable Product)** and are soon going to move on to creating our full project. While I was not able to create a working healthbar, I managed to make it so that when the AI moves and collides with the player's sprite, a random question automatically appears. Below, I explain how we finished the MVP, new concepts learned while doing it and what problems still remain. 

### Enemy AI Attachments
To start off with what I had done, I used `scenes` that Brianna created in order to shift the screen towards a random prompted question and made it so that every time that the player's sprite(`cursSprite`), collided with the AI(`enemy`), it asks you a random question from an array. If you get the question wrong, you arrive at a loss `scene`, while if you get the question right, the game just normally restarts the scene. 

```js
cursSprite.onCollide("enemy",() => {
        go("status-con");
        })
    cursSprite.onCollide("checkpoint",() => {
        alert("Let's test your knowledge!");
        go("check-point-con");
        })
  })
})
 scene("status-con",() => {
       var quesNum = randi(0,11);
       var ques = prompt(conListQues[quesNum]);
        if(ques == conListAns[quesNum]) {
        alert("That's correct!");
        go("plat-one-con");
    } else {
        alert("Study Harder Bozo.");
        go("lose-con");
    }
    })
    scene("check-point-con",() => {
         var quesNum = randi(0,11);
       var ques = prompt(conListQues[quesNum]);
        if(ques == conListAns[quesNum]) {
        alert("That's correct! You're ready to move to the next level!");
        go("plat-one-con");
          } else {
        alert("You'll need to try again..");
        go("lose-con");
    }
    })
scene("lose-con", () => {
	add([
		text("You Lose"),
	])
	onKeyPress(() => go("plat-one-con"))
})
```

### Issues That Were Debugged/Still Need to Work on



### EDP
So far in the EDP(Engineering Design Process), I am at step six which is to **Test and Evaluate the Prototype**. I say this because  me and my partner had already most of the MVP requirements finished. All we had to do was make sure that the game was working properly and debug if necessary. 

###### [MVP Product](https://albertog3410.github.io/sep11-freedom-project/tool/kaboom/kaboom-prompt.html)

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
