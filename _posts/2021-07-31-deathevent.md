---
title: "Death Events"
date: 2021-07-31
permalink: /posts/2021/07/deathevent/
tags:
  - gamedev
  - unity
  - justforfunsies
  - sandbox
  
---

In my [Just For Funsies](https://github.com/JenniTheDev/JustForFunsies) project, I have the player healing and taking damage. So, logically the next thing to do is to kill them off. 

I wanted to make a Player Death event, so when the player’s health is 0, the player dies and the game is over. I ran into a problem though. On my OnPlayerHealthChange event, I pass the struct HealthData, which includes the amount of healing or damage the player is taking. The way I have my events set up, it currently passes some data, but I wasn’t sure what data I wanted to pass, or if I wanted to pass any data at all. 

    ```C#
    public struct HealthChangeData {
        private float changeAmount;

        public HealthChangeData(float changeAmount) {
            this.changeAmount = changeAmount;
        }

        public float ChangeAmount { get => changeAmount; }
    }
    ```
I knew that I could make an empty void type to pass. But, if in the future I wanted to pass data like what killed the player, or any other info, I’d have to go back and fix the type. Instead, I made a struct called DeathData, but left it empty so I could add in the data I wanted later.

    ```C#
    public struct DeathData {

    }
    ```

I also renamed my event from PlayerDeath to Death, since I could check what game object died, and do different things accordingly. Now when the player’s health is <= 0, the Death event is raised. When the Death event is raised, everything in the game that is listening for the Death event does their thing. For now, that’s to switch to my Game Over scene.

    ```C#
    public void CheckForDeath() {
        if (healthPoints <= 0) {
            onPlayerDeath.Raise(new DeathData());
        } 
    }
    ```

As I add in more game objects (like enemies at some point), I can now go back and make a few small changes to make the Death event work differently for each object. Making it a Death event instead of a Player Death event is hopefully the right way to go.  

