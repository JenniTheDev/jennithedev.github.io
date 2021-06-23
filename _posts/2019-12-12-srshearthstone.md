---
title: 'Reverse Engineering a Hearthstone SRS'
date: 2019-12-12
permalink: /posts/2019/12/hearthstonesrs/
tags:
  - papers
  - srs
  - planning
 
---

In my Technical writing class, we got to pick any software we wanted to write a on. My first thought was to do one on one of my favorite games like World of Warcraft, but when I started to think about how you would explain the requirements for a MMORPG I realized I should pick something a little less ambitious. Just for time constraints. 

So I picked [Hearthstone](https://jennithe.dev/files/Hearthstone_SRS.pdf). It's (somewhat) simple to learn, turn base card game. I've played a few times and have hosted a lot of Hearthside gatherings, so I am familiar with the way the game works. Next came hunting down the more technical details of how the game was made. I did this by doing a little bit of detective work with my best friend Google. 

<p align="center">
<img width="500" height="208" src="https://media.giphy.com/media/wZiD4vvJ1yIjKleNnK/giphy.gif">
</p>

One of the first places I looked was for Hearthstone career listings on Blizzard's website. It lists what technologies they use for Hearthstone in all the job descriptions. This is how I learned that Hearthstone uses MySQL, that it was created in Unity and that they use Perforce. It also got me pretty excited to apply for some Blizzard careers in the future. 

Another place I looked was on Youtube. There is a really informative GDC talk titled ["Hearthstone 10 Bits of Design"](https://www.gdcvault.com/play/1020775/Hearthstone-10-Bits-of-Design). It had tons of information on how Hearthstone was designed and what principles they kept in mind. I think the video has important design considerations for anyone creating a game. I watched it quite a few times both for information for my SRS, and for future knowledge. 

Lastly, I also looked at some Hearthstone Game Guides and the Wiki just to make sure I didn't miss anything important on gameplay. 

You can read my [Hearthstone SRS here](https://jennithe.dev/files/Hearthstone_SRS.pdf). 

