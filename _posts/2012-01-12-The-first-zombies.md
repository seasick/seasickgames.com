---
toc: true
layout: post
categories: [Love2D,Lua,Zombie]
title: The first zombies
---


Did I mention, that I love zombies?! So the first game I wrote was a "kill zombies or be killed" game. Could it be, that 83 percent of all first games have zombies within? It had no textures (not counting the blood splatters I used in the menu) and no sound. The "ground" was light grey, the zombies dark grey, the player white and the bullets were yellow.

Drawing some circles onto the screen - yeah, what a challenge ... It got interesting when it came down to calculations on how the zombies should move. Probably any middle school kid would had laughed at me. But having to remember Pythagoras and his guys was serious business. But I managed to get along and get the zombies moving :)

My next challenge was collision detection. Without detection collisions the zombies wouldn't be able to catch me, neither would i be able to shoot them. In addition, the zombies would stack over each other. So whenever a zombie or any other entity changes its position, you need to check against every other existing entity if their outlines are overlaping. This easy aproach has also its disadvantages - the more entities you have, the slower it gets. There are ways to get around that - but more on that an other time.

To sum it up for you:

- Kill zombies
- Every round they are getting faster
- Did I mention bullet time?

Check out the [source code here](https://github.com/seasick/Zombie-Zero).
