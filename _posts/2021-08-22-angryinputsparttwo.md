---
title: 'Angry Inputs Part Two'
date: 2021-08-22
permalink: /posts/2021/08/angryinputsparttwo/
tags:
  - Unity
  - problem solving
  - gameclones
  - gamedev

---
Continued from my [previous post](https://jennithe.dev/posts/2021/08/angryinputspartone/), I couldn’t figure out why my Input System wasn’t working. It came down to a few important things I missed. Here’s what I learned. 

I had the right idea with my Input Action Map. I set it up correctly with Drag’s action being a Value, and Fire’s action being a button. But, I forgot to check the box for generating a C# class. 

![](http://jennithe.dev/images/ABCTwo.JPG)

Then, I didn’t enable my controls or get any reference to them. I originally had this logic in my Ball script, but I didn't think the Ball should be handling the launch action, so I moved it to a Launcher script. I also didn’t use the performed event. Instead I was trying to use a method to read the mouse location or the button click, but I had nothing calling that method.    

```csharp
    var input = new PlayerControls();
            inputMovement = input.Player.Drag;
            inputMovement.Enable();

            inputClick = input.Player.Fire;
            inputClick.Enable();
```

At this point, everything should have been working. I had my script set up to Debug.Log the mouse coordinates every time the button was clicked. But mine still wasn’t. I asked a friend to take a look because I was sure at this point, I was pretty sure it was something small that I was just too frustrated to see. One screenshare and five minutes later, we solved the problem.

I had forgotten to put my script on a game object. I guess I thought Unity would just magically know to use it. I think I also got a little confused with the PlayerControls component. It’s not necessary to use the component, but you do need the script that controls your Input somewhere in your scene.   

![](http://jennithe.dev/images/ABCThree.JPG)

Once I got that fixed, I had to make the Input System work for button press, and button release. [Unity’s documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/Actions.html#started-performed-and-canceled-callbacks) shows how to use the started, performed and cancelled callbacks, and it was really easy to modify my script to show that it works on button press and button release. 

```csharp
        inputClick.started += OnInputClick;
        inputClick.canceled += OnInputRelease;

        private void OnInputRelease(InputAction.CallbackContext ctx) {
            Debug.Log($"Mouse click released at position: {inputMovement.ReadValue<Vector2>()}");
        }

        private void OnInputClick(InputAction.CallbackContext ctx) {
            Debug.Log($"Mouse clicked at position: {inputMovement.ReadValue<Vector2>()}");
        }   
```

Now I can continue onto creating more of my [Angry Birds clone](https://github.com/JenniTheDev/AngryBirdClone). Plus, I now know a lot more about how to use Unity’s new Input System than I did before.  

![](https://media.giphy.com/media/4Vv0DBDoPELGjy8dWT/giphy.gif?cid=790b761194af80c0ecf222ecbda52aa86331b3fd679c66e1&rid=giphy.gif&ct=g)