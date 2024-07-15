---
layout: post
title:  "A puzzle game, the story so far..."
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
- The biggest change from Picross, would be that the player instead of marking spaces, would place polyomino tiles (think *Tetris*) on the grid.

## The journey with picotron

## Conclusions so far

### What's next

[Picotron]:https://www.lexaloffle.com/picotron.php
[Fit to Print]:https://boardgamegeek.com/boardgame/352574/fit-to-print
[Against The Storm]:https://en.wikipedia.org/wiki/Against_the_Storm_(video_game)
[Opus Magnum]:https://en.wikipedia.org/wiki/Opus_Magnum
