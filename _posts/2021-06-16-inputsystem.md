---
title: "In Put"
date: 2021-06-16
permalink: /posts/2021/06/inputsystem/
tags:
  - sandbox
  - unity
  - gamedev
  - justforfunsies
---


Since school is out and I have graduated, I decided I would start a sandbox type project where I could try out all the cool things I let other people do. I think I just missed having a project to ~~procrastinate~~ work on. 

My [Just For Funsies](https://github.com/JenniTheDev/JustForFunsies) project might turn out to be something cool, or it might not. For now it's just a blank slate. I've been taking what I learned about Scriptable Objects in my [Microverse](https://github.com/JenniTheDev/Microverse) project, and applying it to my Funsies project by making two ground squares that add or take away health. 

But before I can get to testing anything, I needed a player and a way to move that player. I haven't used the new Input System that much (I've mostly given that task to others because it fit what they were doing), so I knew I wanted to use it. It's the best choice in how flexible it is, and I like knowing that a person can use a controller or a keyboard to play my game. It's the way to go. Except I have very little idea on how to implement it. 

I started my research by looking at YouTube tutorials. It's really hard to find a good tutorial. It's even harder to find a good tutorial about the new input system and how it works. I followed along one video and got a buggy controller that only worked backwards from my WASD keys. Another had all the logic in the Update loop. Que up a few that were outdated, difficult to follow, or not really what I was trying to do. 

After following a few tutorials and telling myself I'll just refactor once I have something that somewhat works, I moved onto reading the documentation. It was pretty interesting, but I still don't have a working input system. I did learn about how you can make Action Maps for different things. It made me think about the problem I had with my ShaderLand character. It can't click on UI buttons. I'm pretty sure that I can now go fix that, but that doesn't help me with my current lack of a working input system. 

I know I want a character that can walk in all directions, look around, and jump at the very minimum. Do you have a video or resource about Unity's new Input System? If you do, please share!