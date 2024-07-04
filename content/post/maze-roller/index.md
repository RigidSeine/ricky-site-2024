---
title: "Maze Roller"
description: A Unity game where procedural generation is the name and the aim.
date: 2024-07-04T22:59:13+12:00
image: MazeRoller_preview.png
tags:
  - C#
  - Unity
  - Game
---

Maze Roller is a game where a player guides a ball from the start point to the goal point by rotating the maze a la the labyrinth marble game.
The aim of this project was to implement an algorithm that procedurally generates a new maze on every game.
The specific algorithm used for Maze Roller consisted of using quad-edges, a graph and its dual graph to build the maze, and depth-first search to traverse it.

<h4>
    Click onto the game to take control. Use WASD keys to rotate the board and move the ball to the goal!
</h4>
<h4>
    Press the 'r' key to reload the level and see the maze take on different forms.
</h4>

<div>
    <iframe src="https://rigidseine.github.io/MazeRoller/MazeGenBuild_1-1WebGL/" width="100%" height="680px" title="maze-gen" scrolling="no" overflow="hidden" allowfullscreen="true">
    </iframe>
</div>