---
title: "In Put Again"
date: 2021-06-19
permalink: /posts/2021/06/inputsystemtwo/
tags:
  - sandbox
  - unity
  - gamedev
  - justforfunsies
---

The second time is the charm? 

In my [Just For Funsies](https://github.com/JenniTheDev/JustForFunsies) project, I was having difficulties getting my input system to work for my Player Character. It was really a combination of it not working (aka, I'm doing something wrong), me trying too many different ways at one time, and lack of direction. I have a general idea of how the input System works, so I decided that I really just needed a working input system so I could move onto the other things I wanted to do.

My first attempt was to take the Input System from my [ShaderLand project](https://jennithe.dev/portfolio/3-shaderland/), because it's the one that comes with the Unity Shader Demo. It worked great in that project, so I figured I could just drop the parts I wanted into my Just For Funsies project. It looked like I had a great idea until I tried to make my ground colliders work. They didn't. After a lot of debugging and some extra sets of eyes, I figured out that my Player only collided with itself, not anything else. After showing the script to another Developer, we agreed it was probably best to not use it and come up with something else. 

After some more discussion, I decided to try out Unity's [Starter Assets - First Person Character Controller](https://assetstore.unity.com/packages/essentials/starter-assets-first-person-character-controller-196525). There is sometimes no point in reinventing the wheel, and I decided at this point I just wanted to move on with my project. I added the package to the game, then tested that the Input System, Character and Camera all worked correctly. I added my PlayerCharacter script, walked over the stuff on the ground... and nothing happened. 

This meant more debugging. I checked over the PlayerCapsule to see if it was missing anything, and I checked the Capsule Colliders and all of the Transform Positions. It looked like I had two different Capsule Colliders stacked on top of each other, so I fixed it so there was one. I also noticed there was no Rigidbody. Once those were fixed, my stuff on the ground worked perfect. 

I then adjusted my UI to update the PlayerCharacter Health when the OnHealthChange event happened. I also changed my OnColliderEnter to OnTriggerEnter. It's not an object my player needs to push, pull or jump on. It just needs to trigger a change in the Health of the Player (like standing in lava or on a buff). 

![](https://media.giphy.com/media/hUZ32FYDhFfDukQAlR/giphy.gif)

Now I can move on to the other parts of my project I want to work on, like making more events, adding enemies, and adding sound to my triggers. 