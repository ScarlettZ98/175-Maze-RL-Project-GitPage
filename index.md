# CS 175 Project Proposal
Shawn Kooklan 77621849

Amitesh Arora 53422821

Scarlett Zhang 66108402


## Project Summary

Inspired by the video _[Tabular Q learning using Malmo in Minecraft](https://www.youtube.com/watch?v=Iloh8MV-WvY&t=101s)_, we want to develop a smart agent which can walk around a complex maze and reach the goal with the smallest cost. 

Our agent should be able to:



*   Take the current view of the game and return an action among moving left, moving right, moving forward, moving backward, or attacking.
*   Find an optimal path through the maze in a given amount of time.

The maze is a 20x20 square plain surrounded by lava. The goal is represented as a diamond block. The start and goal states are placed on opposite edges to one another. The agent must reach the diamond in order to succeed. There are also trees as obstacles, which require the agent to either avoid them or destroy them. Up to 40% of the maze can be trees. 

![pixil-frame-0 (1).png](https://i.loli.net/2020/01/28/ITBt6QsxLJgvN9V.png)


_Figure 1. Example of Maze. Red: Lava, Brown: Tree, Blue: Goals, Grey: Agent_

When the agent reaches the diamond block or steps into the lava, the game restarts. 

## Evaluation Plan

### Quantitative evaluation

We would try Q-learning as our approach first. We will design multiple test cases with different difficulties, e.g. an easy maze without trees and only one goal, and a maze with layers of trees and multiple goals. Every move costs 1 point. Dropping into the lava costs 10000 points because it is the worst. Reaching the goal brings 10000 points as the reward. The agent can also cut a tree to explore a new path and this action costs 15 points. We might adjust these values while working on this project to get better performance. The baseline of our project is that the agent can find a goal without cutting a tree. The expected result is that the agent can find a goal with the least cost. If the way is blocked by trees and it takes more than 15 steps to circumvent the obstacles, then the agent should choose to cut down the tree. We may try Deep Q-learning if the performance of Q-learning is bad or the memory is not enough. 

### Qualitative evaluation

We will monitor the values of positions with visualizations. The agent should recognize the view of the game and convert it into an understanding of the 2D map of the maze. The sanity check cases are mazes with at most 60 trees (15%), the agent should find the least cost path to reach a goal in a reasonable amount of time. A moonshot case is one with around 160 trees (40%) and multiple goals surrounded by layers of trees. 



![pixil-frame-0 (3).png](https://i.loli.net/2020/01/28/ey6vSVoBX3lmKa4.png)
![pixil-frame-0 (2).png](https://i.loli.net/2020/01/28/plOE5xizP68fZvW.png)


_Figure 2. Sanity Check Case Example & Moonshot Case Example_

## Goals

### Minimum goal
Build an agent that is able to successfully solve a fixed, simple maze.

*   Milestone 1: Design a working maze and build the framework for testing an agent within a maze.

*   Milestone 2: Perform learning in order to have the agent successfully solve the maze and reach the diamond.

### Realistic goal
Add difficulty to the maze by increasing the number of obstacles and making it randomly generated.

*   Milestone 1: Adjust parameters and optimize training to account for random generation of more complex mazes.

*   Milestone 2: Perform training and evaluate the agent's performance when solving a higher complexity maze.

### Ambitious goal
Add high complexity to the problem by adding destroyable blocks such as trees to the maze which the agent must decide to avoid or destroy. The agent can also craft items with materials to aid in its solution.

*   Milestone: Adjust policy and train agent to account for the option of destroying blocks and crafting items.
