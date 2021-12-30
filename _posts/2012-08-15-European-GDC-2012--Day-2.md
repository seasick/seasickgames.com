---
toc: true
layout: post
categories: [Games]
title: European GDC 2012 - Day 2
---

AAA goes F2P: Same skills, different mindset
============================================

The guy who held the talk, is a former journalism student, who didn't get a job as journalist and ended up in the AAA industry, participating on various titles like "Total War".

Free 2 play is all about game mechanics. You need to earn the users will to pay for it. Only nice and shiny graphics wonts sell.

There is a "3 Minute Hook", in which you need to be able to get the player into your game. Kinda remembered me of the low attention span from a talk yesterday (5 reasons ...) - but in this case it was somewhat different. When a player buys a retail game in a store, he is paying 30-60€ for it. Don't playing it would be like flushing money down the toilet. So players are willing to give the game a try. In a F2P game, you won't have this generosity. You need to get the player hooked as soon as possible -- otherwise you will lose him. He talked about that 70% of registered players will stop playing at the 4th day.

One of the hardest parts in F2P is the fact, that you have to deal with different players, who have a different background and skill set. This makes balancing very very hard. So you will need mechanics which will prevent the gap between those players becoming to big. That could mean bonuses for bad players and subtle mechanics to hold "too good" players back. But this could also be very dangerous.

Addiction is the key to keep players playing (and paying). There are several approaches to this

-   People want to feel needed, if there is nothing to do, they will stop playing
-   People need to feel, that they want to check on the state of the game. Is someone attacking me? Is my building ready?
-   Community!
    -   It is easy to give up a game -- but it is hard to give up friends. Even if you met them online.
    -   Know what is going on in your "area" (Activity stream)

Secret souce for location based game's feature ...
================================================

... learning from *Shadow Cities*. Shadow Cities is a game from a Norwegian company. The speaker didn't gave any numbers on their players, but told us, their game is played in over 40 countries (numbers would have been real nice).

Location based doesn't (exclusively) mean that you play on a real map where you are. Every game which handles real life locations could be seen as location based.

The speaker talked about eight key "ingredients", when it comes to location based games.

-   The critical mass challenge
    -   If no one is playing in your city, you will feel alone, and will stop playing. Deal with it! In Shadow Cities, you can teleport to your friends.
-   The sense of location
-   The open world vs. curated experience
    -   Thus you have such a big world, you can easily feel lonley (critical mass), but it also can get cluttered very fast.
-   Stationary vs. movement
    -   Most of the people play their game from home and work (76%)
-   Playing with neighbors
    -   Strong emotions
-   Geodata
    -   Where do you get your data from? Openstreetmap is a good choice, but isn't 100% reliable. Before you begin planning such a game, you need to have a look at the data, if it is even possible.
-   Infrastructure: Battery, positioning and latency
    -   GPS is battery sucking bitch!
-   The brite social graph
    -   Again it comes down to balancing. In location based games, it is even harder, because you could achieve a balanced distribution of power in a country, but does this make your city or neighborhood also balanced?

Post Mortem: Developing a city builing game ...
===============================================

... thats ready for quick content iteration. That speak was a ... yeah ... SHIT! The outline for this talk seemed really interesting, but most of the topics were only touched slightly or never mentioned. In addition I often did not understand the speaker.

So here is what I could take from this talk

-   Lot of iterations
-   Minimize the gap between what the user wants, and what you provide
-   Parallelize planing & design
-   In order to scale design, the company shares all design documents with all the designers. Even back to 2005.
    -   Every design decision could be understood

The Voodoo art of dynamic WebGL
===============================

Awesome talk, awesome dude (another guy who participated in making Lemmings :)). But I think I went over my head, when I went into this talk - since my knowledge of WebGL is very limited. Besides some IE9 bashing (using Chrome Frame is the only solution - every thing else isn't worth it) here a short list what I took away from this talk.

-   Your GPU is powerful - let it have it. All the time. You are doing something wrong (or you have so less to render :)), when the GPU has nothing to do.
    -   Use batches of commands
-   Sprites (ok, nothing new)
    -   When you make your sprites/texture pages, sort the pictures per size.
    -   Big pictures first, starting in the upper left corner.
    -   Add borders/padding to pictures to avoid unexpected behavior, when you scale an image.

Of course there was way more in this talk. Waiting for the slides :P

Love engine postmortem:
=======================

Lean and mean C engine design. The guy who held this talk, kinda surprised me. He sees things very differently than most of us. The talk wasn't only about his engine - it was also about how you should develop things. There are a few quotes/things i want to share with you.

-   Great code is not written, it is rewritten
-   C++ should be named ++C if it really was any better than C
-   API is the key to collaboration
-   Code which makes fun to write should be written again, Code which doesn't make fun to write, should be written in a way it is reusable
-   Engine decisions affects the game design
-   Technology unlocks creativity.
-   Engines should be throw aways
    -   Developing an engine is inexpensive (A couple of engine engineers vs. hundreds of artists)

Cheaters, hackers, script kiddies ...
=====================================

... the dark side of online games. The talk started interesting, but as the speaker started talking about SQL injections, I left and decided to have a look at the dom of cologne :)
