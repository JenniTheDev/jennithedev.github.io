---
title: 'Angry Inputs'
date: 2021-08-17
permalink: /posts/2021/08/angryinputspartone/
tags:
  - Unity
  - problem solving
  - gameclones
  - gamedev

---

Make an Angry Birds clone, they say. It will be fun, they say. 

I was undecided on what I wanted to do next on my [Funsies project](https://github.com/JenniTheDev/JustForFunsies) when a friend suggested that making an Angry Birds clone could be fun. I thought that sounded like a great thing to try. I found a [Brackeys](https://youtu.be/QM8M0RainRI) tutorial to make one, and started following along, making changes to use all the Unity skills I’ve been learning. 

I came to the part of the tutorial that covered Player Input. Since the video is older, it used Unity’s old input system. I wanted to use the new input system so I could get more practice with it. 

In the video, Brackey gets the position of the mouse with a method OnMouseButtonDown, and then sets the RigidBody of the projectile bird to that position. I needed to figure out how to do this with the new InputSystem. I made my PlayerControls and gave it two actions- Drag for the mouse position, and Fire for the mouse button click. I then tried to use the Drag action to set the RigidBody to the mouse position. It didn’t work.

[](http://jennithe.dev/images/ABCOne.JPG)

I kept getting compiler errors for assigning the mouse position, and I’d fix that and get some other errors. I decided to step back and see if the mouse was being recognized at all by putting out Debug.Log for my mouse click. I got that part working by using the OnClick of the UI Input System that Unity makes for you. That wasn’t what I was going for, but it was something.

*This is not right, at all*
```csharp
private void OnClick() {
        // this needs fixing for Press down and press up
        // this click counts for press down and let go
        if (pointer.IsPressed()) {
            isPressed = true;
            Debug.Log("pressed click");
            rb.isKinematic = true;
        } else {
            isPressed = false;
            Debug.Log("pressed click");
            rb.isKinematic = false;
        }
    }
```    

I figured maybe reading the [documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/QuickStartGuide.html) for the new Input System might help. Sometimes if I look at the different properties and methods there are, I can use those to figure out my problem. It didn’t work this time. I googled, but didn’t find anything helpful to my situation. 

The more I googled and read, the more I found myself wandering off course and not solving my problem. I knew I needed to narrow things down. I needed to know when the mouse button was being clicked down, and when it was released. I needed to know the Vector2 position of where the mouse was. I had these set up in the Input system, but I couldn’t figure out how to connect the actions to my game. 

Can you guess what my problems were? 

