---
toc: true
layout: post
categories: [Unity]
title: Unity - First steps
---

So I wrote yesterday evening about unity. After I published the post, I started to make a little Jump'n'Run. I think it is a good way to get to know unity, because it covers a wide range of needed features:

-   Camera movement and controll
-   Controlling "the player"
-   Collision detection (unity does all the heavy lifting for you)
-   Triggering death and finishing a level
    -   Loading new levels on success
    -   Reloading the level on death
-   Collection points while running through the levels
-   Animation (I animated the "coins" to bounce up and down)

What did I learn from this?

-   When you want to do an animation on a prefab ("template" for assets) you need to create the animation on it, but you can only changes the values on an existing GameObject. Furthermore I noticed, that I needed the prefab to be contained into a parent. Otherwise the animation will work with absolute values, and all your GameObjects which inherit from this prefab, will be in one place (at least if you have a positioning animation). With a parent, the positioning will work relative to the parent. Took me a while to figure this out .
-   The community is great, and seems to be very noobie friendly (as long as you care to search first)! Every question I got was asked before, no need to ask for myself :)
-   Controlling the character takes a lot of time to tweak. And as you can see, I didn't managed to do it the right way. The controls are still a little bit blury.
-   There isn't realy much coding.

Today I tryied out the building options - As you can see I attached here a build of the web player. Control your "character" with WAD (yeah, there is no S :) ), jump with space. It is a bit small, but it demonstrates how quickly you get something to show with unity.

There is surly enough space to polish this up, but it wasn't ment to be a finished game. Just something to learn from.

Next up ... maybe I'll try a breakout clone. I'm sure there is something to learn from :)
