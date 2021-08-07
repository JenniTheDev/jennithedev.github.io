---
title: "Fade to Black"
date: 2021-08-01
permalink: /posts/2021/08/fadegameover/
tags:
  - gamedev
  - unity
  - justforfunsies
  - sandbox
  
---

In my [Just for Funsies](https://github.com/JenniTheDev/JustForFunsies) project, I decided I wanted to learn to do scene transitions. So since I have my Game Over event, I made a Game Over scene to go with it. 

Usually I have my Game Over menu as a canvas that comes up over my game scene. This time I wanted to give it it’s own scene and do a scene transition to it. I know that [Empyrion](https://empyriongame.com/) uses a sort of lightspeed effect to do their scene transitions, so I thought it would be a good thing to learn. Since my player has died, I went with fading to black. 

![](https://media.giphy.com/media/hQAXty4hgoWf0xaPKZ/giphy.gif)

I made my new scene and put in a canvas for my Game Over words. I realized if I faded to black and had a black background on my new scene, it made it look like the Game Over words were fading in. Once I got the animation finished, the scene transition timing right, and everything working, I added two buttons for playing again and exiting the game. 

And then my buttons didn’t work. 

I feel really confident about my button making abilities in Unity. I’ve made a lot of buttons that do all sorts of different things, especially changing scenes. So I started troubleshooting. 

First I tried using a Debug.Log to see if the button was registering the mouse click. It wasn’t, so I immediately assumed it must be my input system. I have a love-hate relationship with the new input system, and I’ve had problems with it before. I read the documentation and watched a youtube video on it. It still didn’t work. 

I was about to go ask someone to look at my project, but I took a look at my GameObject first. My UI game object had one canvas that had the Game Over words, and a different canvas that was for my two buttons. At that point, it hit me and I had to laugh. You can’t click on buttons when there is a canvas layered on top of them. 

I moved everything onto one canvas (like I should have done in the beginning), and everything worked perfectly. I also got a good laugh at myself out of it. 
