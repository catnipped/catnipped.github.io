---
layout: post
title:  "A logic puzzle game, the story so far..."
date:   2024-07-15 12:00 +0200
categories: logicpuzzle
---
## The "picross-like" pitch

![recent screenshot of puzzle game](/assets/puzzlegame/2024-07-15-screenshot.png)

Usually when I take on a game idea it's been brewing for quite a bit in my brain already. I often come up with new ideas while doing dishes or taking a shower (or more begrudgingly, while trying to sleep). I jot them down, or just put them aside and forget about them, then they pop up again a long time later, in new form or shape. Some aspects always persist, and that's usually the thing I try to stay true to when I do start working on something.

This game idea started out as an off-shoot from trying to start something in Unreal 5, inspired specifically by *Picross 3D*. I love that game (and the other Picross games), and would play *Picross 3D Round 2* on my 3DS every night before going to sleep. It was a kind of logic puzzle where you always feel like you're progressing, chipping away at the puzzle until you finish, and then you start over. It just kind of... stimulates and tickles the brain, without being too heavy or involved. I wanted to do an evolving logic puzzle game that gave the same feeling, but with a meta layer where each solution would build towards something else (think upgrade trees, or completing objectives).

![Picross 3D Round 2](/assets/puzzlegame/picross-3D-round-2.jpg)
*Picross 3D Round 2* by HAL Laboratory

Anyway, the idea was too big, and needed to be scoped down, so I could prototype in an environment that I felt more comfortable in. This was in March, and *[Picotron]* had just came out. I have experience with *Pico-8*, which is very similar (importantly, you code in Lua). So it felt natural to try to do the "Picross-like" in Picotron instead, reducing the idea to a 2D game, and with some other twists inspired by games I recently played (and loved), namely *[Fit to Print]*, *[Opus Magnum]* and *[Against The Storm]*.

![Fit to Print](/assets/puzzlegame/fit-to-print.jpg)
*Fit to Print* by Flatout Games

![Opus Magnum](/assets/puzzlegame/opus-magnum.jpeg)
*Opus Magnum* by Zachtronics

![Against The Storm](/assets/puzzlegame/against-the-storm.jpeg)
*Against The Storm* by Eremite Games

Fit to Print is a tile laying board game where players try to get points by placing different sized tiles, or "articles" on a grid (representing the front page of a newspaper). Each tile has rule for where it can be placed to score points. It's a really fun puzzle to solve each time.

Opus Magnum follows the same setup as many of the Zachtronics games, where you have to build a machine that produces an end result, puzzling together the machine from pieces of various costs and programming it to get the result as quickly as possible. What comes out of it is that the gameplay is very freeform, the puzzles can be quite involved and hard to solve, but each solution is unique, and you can almost always optimise the machine you build to become faster or cheaper, later on. I really like this approach as the game beocmes more flexible and replayable. It's up to the player when they want to move on to the next puzzle.

Against the Storm is a city builder with a roguelite structure that is just a joy to play. What I felt the most inspired by in this game was the way it has a bunch of smaller systems that all relate to each other, gently pushing and pulling. It's also up to the player how and when they want to ease into them. Sometimes I just want to not think much and build a town, complete some objectives, and sometimes I want to really think and engage with the systems for greater rewards. You're always progressing in some way.

So yeah, an idea for a "picross-like" with some twists started to form:

- The player should be able to fairly easy meet the requirements to "finish" the puzzle, but can optimise the solution. This means that puzzles need to be quite flexible, without single solution.
- The game should have a meta progression layer that ties into the logic puzzling, including optional objectives.
- The biggest change from Picross, would be that the player instead of marking spaces, would place polyomino tiles (think *Tetris*) on the grid, and these tiles would have different added rules and effects (like the articles in Fit to Print).

## The journey with Picotron

I won't go into detail about Picotron in this log, but the short is that Picotron is a "fantasy console", basically an old school gamedev environment that can also be used to play any of the games (or "carts") made with it. Fantasy consoles generally have some enforced restrictions of what games you can make in terms of graphics and processing power, to limit the scope of what you're making. The biggest upside to this is that they are generally approchable and easy to use and allow for very fast iteration (no build times).

When I started out with this project, I focused on getting to the point where a player could fill out a puzzle with polyomino tiles.

### The first days of development

![First gif from prototype](/assets/puzzlegame/2024-04-20-first-steps.gif)
Placing tiles with collision checks.

![Level editor](/assets/puzzlegame/2024-04-27-level-editor.gif)
![Level editor](/assets/puzzlegame/2024-04-27-level-editor.png)
I wrote some code that that turns sprites into picross puzzles, and a basic version of the evaluator that checks if puzzle has been solved.

![Rotating and deleting tiles](/assets/puzzlegame/2024-04-28-rotating-deleting.gif)
I then added the ability to rotate tiles, and to switch modes so you could remove placed tiles. Here you can also see a first version of a kind "score counter" based on what tiles you place. The idea is that bigger tiles, which are harder to fit, are worth more points.

![Marking empty spaces](/assets/puzzlegame/2024-04-29-2-evaluating.gif)
Every picross-like needs a way to mark which spaces must be empty, so I added another mode for that (-).

![Changed UI](/assets/puzzlegame/2024-05-05-ui.gif)
I made a "toolbox" where you can inspect and switch which tile to place, and UI to show which tool you're currently using (inspect, place, erase, or mark empty)

## Conclusions so far

![recent screenshot of puzzle game](/assets/puzzlegame/2024-07-15-screenshot.png)
Here is how the game looks so far. A theme has started to form, of being some kind of artificer, where each puzzle is a circuitboard the player needs to fill out with components. Components would cost money to place (or rather, would add up to a bill the player needs to pay at some point), and each components would generate energy or **compute** that, in the end, would get the player more money, hopefully getting a profit.

I got some small ideas for a name, but nothing has stuck. The best one so far is *Electrojunk*, the theme being that you are some kind of electronic scrapyard worker, peicing together cool new circuits out of old parts, a "junk punk". But since the word junk is slang for genitals... I think i'll try to find something better.

![electrojunk logo](/assets/puzzlegame/electrojunk.png)

I have identified already some problems with where the current prototype is, the main one being that the picross puzzles need to be quite simple so the player can focus on the optimisation puzzle. This then causes the picross "layer" to be quite quick and dull. I think I might need to rethink how I want to portray the picross puzzle. And I would like to try something that is initially much simpler, adding row and column restrictions in some other way. We'll see!

### What's next

I've not worked on the game for a couple of months now, and it will likely be some time before I get back to it. Part of the reason for writing this devlog is so coming back will be easier!

Right now I'm excited by the prospect of doing away with the picross numbers, to focus on effecient tile laying, maybe even turning the level editor into creating the circuit board shape instead. I really need to "find the fun", which I believe is here, but maybe not in its current shape.

Another thing I'm looking forward to is designing and implementing that meta progression layer: optional objectives, an economy of tile prices, electricity usage (adding "battery" tiles), and "compute" generation.

Anyhow, thanks for reading! I hope I get back into this project in the future!

[Picotron]:https://www.lexaloffle.com/picotron.php
[Fit to Print]:https://boardgamegeek.com/boardgame/352574/fit-to-print
[Against The Storm]:https://en.wikipedia.org/wiki/Against_the_Storm_(video_game)
[Opus Magnum]:https://en.wikipedia.org/wiki/Opus_Magnum
