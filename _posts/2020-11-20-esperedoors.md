---
title: "Espere's Journey - When One Door Opens"
date: 2020-11-20
permalink: /posts/2020/11/esperedoors/
tags:
  - espere
  - unity
  - gamedev
---


I had thought I had worked out the door puzzle problem in [my previous post](https://jennithe.dev/posts/2020/11/esperepuzzles/), but they weren't working as well as I wanted. It also seemed really unnecessary to be using keys to open the door when we weren't giving the player any sort of key. 

Plus there were other problems. If an enemy stood on a trigger, it would cause the door to open or do some unexpected behavior. The player could walk over the trigger and trigger it multiple times. The entire system couldn't be reused on different doors without bugs (I never did figure out why door three would always open door four, no matter what I changed). My doors also needed audio and animations. The engineer in me never considered the doors would need animations, not just simply being open or closed. I want to keep my designer happy(and my game playable), so I reworked my doors into an entirely new and improved system.  

After talking it over with the designer and some other developers, I decided to make a class, Door. Then my different types of doors can inherit from the Door class. The Door class handles opening the door and checking the order of triggers if needed. That way I can use it on doors that just need to open, or need triggers to open, or need a specific set of triggers in order to open. It also removes the need for managing keys unnecessarily. 

Code is simplified for space, but you can [view the full code here](https://github.com/JenniTheDev/EsperesJourney/blob/dev/Assets/Scripts/Door.cs).

```
protected virtual void OpenDoor(){
  // To be used by each door
}

private void UpdateTriggers(){
  // Add trigger to Array, check if order is forced and if order is correct
}

private void CheckDoorLock(){
  // Check if all Triggers are triggered and then call OpenDoor
}

private bool TriggeredInOrder(){
  // Check the trigger order and return true if it is, false if it isn't
}
```

I then use this door class to make different types of doors - A delay door, an immediate door, an open only door and a bridge door. Each door can do it's special thing, and call on the Door methods to check triggers (or not) and then Open. The script for the kind of door gets placed on the door object, and then any number of triggers can be used to open the door. 

![](https://media.giphy.com/media/VlgCEzzO5PFrYXuLKG/giphy.gif)

I've only used inheritance in C++, so to learn to apply it within Unity, C# and Game Dev was an eye opening experience. I am going to flex this skill on other projects in the future. 


