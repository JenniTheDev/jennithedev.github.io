---
title: "Espere's Journey - Puzzling Over Puzzles"
date: 2020-11-09
permalink: /posts/2020/11/esperepuzzles/
tags:
  - espere
  - unity
  - gamedev
---


One of the tasks I was given in the Espere's Journey project was to manage the environmental props that the character would be interacting with. I made all of our environmental props into prefabs, and for fun, created a door that opened with a key. Once the player had the key, they could go through the door and it would open and close. When I asked the designer about how they wanted the puzzle room to work so I could set up the prefabs in there, he surprised me with not just one puzzle room, but five additional puzzle locked doors. Since I like a challenge, I told him I would figure it out and make them work. 

### Puzzle Specifications

Upon getting the specifications, I could see the puzzles fit into three categories. Three of them were pretty basic doors that just needed a trigger to open or close. Two of them took four actions in a certain order to open. One had to have two actions done to open the door. I decided I would start with the basic doors first, and hoped that I would be able to create flexible scripts that I could use on the more complicated doors. 

To get a good idea of the puzzles in order, here is a short walkthrough video of them. I'll refer to them as puzzles One through Five, and the Boss Door, since that's the way they are organized in my test scene. 

<figure class="video_container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/NawARkH-GFY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</figure>


### Puzzle One and Puzzle Five

Puzzle One was simple. The Player steps on the blue button in front of the door, and the door opens. I created a trigger with a script, and a door object. I learned from my door with a key test run that the trigger and the door needed to be two objects. I used an interface with my trigger and the door, and decided that my door objects would only do door things - open and close. 

Puzzle Five was a similar door system. When the Player enters the room, the door was supposed to close behind them, and in front of them, trapping them in the room with an enemy. When the enemy is killed, the doors will open. I made a new set of game objects and reused my scripts from my first puzzle. In trying to reuse my scripts, I realized I had situations for when the door was open and needed to close, and times when the door was closed and I needed it to open. I already had a script for doors that opened and closed, and I wrote one for doors that needed to open. I was about to write a script for doors that needed to close when I stopped to think about it. It wasn't about a door opening and closing, it was that the game object needed to be the opposite of what it was. I rewrote my script and was able to use it on every door throughout the level. The Boss Door benefited from my new script and it was quick and easy to set up. 

### Puzzle Two

This lead me to Puzzle Two. The Player needed to push both buttons at the same time to open the door. Since the Player can't stand on both, they need to push a box on one. Since I planned that the door object would only open and close, then trigger needed to handle the logic behind what is allowed to open the door. I made the door trigger check if both the left and the right triggers were entered by an object on the Player Layer, and if it passed the Permission Check, the door would open. Once I got this working, it was time to handle the last two puzzles.

### Puzzle Three and Puzzle Four

Puzzle Three and Puzzle Four both involved four actions a player must do in order. Puzzle Three has four tiles that must be stepped on in the right order to open the bridge. Puzzle Four has a statue that plays a tune, and the Player must step on squares to play the notes in the right order. Both would need the same things, a list that contained the unlock order and a list of what order the Player touched. I knew that I wanted to use lists so that my script would be flexible if I used it in the future, or had to change up the puzzles. I was a bit stumped over how to handle putting something in a list and checking it against another list. It occurred to me that I already had made a key, so I changed it into a list of keys. I then put a different color key on the tiles they needed to step on, and turned off the sprites. That way the player can collect their invisible keys into a list in order, and then I can compare this list against the list on the trigger that opens the door. If the order is wrong, then that trigger resets the keys on the player and plays a sound so they know it was incorrect. 

Puzzle Four uses the same key logic, but with an addition. I made those keys have audio clips on them. The statue plays the tune the Player needs to match. Instead of having the entire tune on the statue and one clip on each key; I made the statue have a playlist of the four clips in order, played one after the other like a song. This cut down on the Sound designers work, and left it open if we wanted to have more then four sounds to hit in order. Now, when the Player collides with the key, the key is added to their list and the sound is played. The trigger by the door checks the key order. As before, if it's correct the door opens, if not the list is erased and the error sound is played. 

### It works...for now

This gives us our six puzzle doors. As we are in the prototyping stage, I know that I will need to go back and refactor a lot of my scripts. The entire puzzle system should be communicating using the event manager. I have some scripts that I wrote and never used. I'm also sure there has to be a more efficient way to handle having the player flip switches in an order. It was very enjoyable to figure out how to program these puzzles, and I hope that they are fun for our future players. 

The GitHub for this project can be found [here](https://github.com/jenniferafelton/EsperesJourney).



