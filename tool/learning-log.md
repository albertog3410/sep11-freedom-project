# Tool Learning Log

## Tool: **Kaboom**

## Project: **Platformer Input Game**

---

### 9/30/2025:

* You can edit a property's behavior by clicking the triple dots and go to "Edit Behaviors".


### 10/3/2025
Task: Find way to implement Javascript into Gdevelop

* Found Github folder that shows how to implement <a href="https://github.com/4ian/GDevelop/blob/master/newIDE/README-extensions.md">Extenisons to Javascript code</a>



### 10/8/25:
* Video I found on how to use  <a href="https://www.youtube.com/watch?v=cv3qn-M4OH0">Javascript with Gdevelop</a>
* Already Downloaded Gdevelop into IDE.
* Extenisons can be found when designing game on the website.
Try and Find time to ask on Slack channel about Gdevelop.

### 10/10/2025

* Gdevelop has not been working out due to complex code that did not really help me create what I wanted.
* Switching to <a href="https://phaser.io/tutorials/getting-started-with-phaser-launcher"> Phaser</a>.



### 10/30/25
* Phaser keeps redirecting me towards making an account in order to use phaser editor.
* Once I have time, I will through <a href="https://github.com//phaserjs/editor-scripts-quick"> Phaser's github editor</a> to see if I can download and use javascript components.


### 11/13/2025
* CDN package template to start with when creating a game for Kaboom

```js
<script type="module">

// import kaboom.js
import kaboom from "https://unpkg.com/kaboom@3000.0.1/dist/kaboom.mjs";

// initialize kaboom context
kaboom();

// add a piece of text at position (120, 80)
add([
    text("hello"),
    pos(120, 80),
]);

</script>


```

* `kaboom()` intializes the context of Kaboom.
* `add([])` adds in the context.



* Ask on Slack Channel if there is a way to use the images shown in the tutorial webpage. <a href="https://kaboomjs.com/doc/setup"> Kaboom </a>
* 


<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
