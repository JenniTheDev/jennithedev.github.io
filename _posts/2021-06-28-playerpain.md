---
title: "Ouch, Ahhh, Ouch, Ahhh"
date: 2021-06-28
permalink: /posts/2021/06/playerpain/
tags:
  - gamedev
  - unity
  - justforfunsies
  - sandbox
  
---

I wanted to play a sound effect when the player takes damage and when they are healed. I was originally going to put the sound effect script on the game object that was causing the health change, but I ran into a problem. 

When I put the sound effect on both of my ground objects, they would play their sound at the same time when the trigger was entered. Using the Events and Delegates pattern (my favorite), I have an event OnHealthChange, that is raised whenever the Player’s health changes. Both ground objects are listening to this event. Every time the event is raised, they would play their sound effect. 

The more I thought about it, it seemed more logical that the player would be making a sound to show they were healed or damaged, not the trigger. For example, lava would make a lava sound, it wouldn’t be there silent until you stood in it. So, I moved the script that would play the sound effect to the player. 

With the OnHealthChange event, I get the ChangeAmount of the HealthChange.The Player then listens for that change and then plays the correct sound. If the change is less than 0, it’s a damaging sound. If it’s above 0, it’s a healing sound.

I went one step farther and made a list for each of the HealthChange sound effects so it can randomly pick a sound each time it’s used. I think this gives it some variety. 

<iframe width="400" height="225" src="https://www.youtube.com/embed/_xn0oVZGTUM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Now that I have solved this problem (for now), I can move onto my next Event - Player Death. 






