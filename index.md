# CS 175 Project Proposal

**Project Summary**

Inspired by the video _[Tabular Q learning using Malmo in Minecraft](https://www.youtube.com/watch?v=Iloh8MV-WvY&t=101s)_, we want to develop a smart agent which can walk around a maze and reach the goal with the smallest cost. 

Our agent should be able to:



*   Take the current view of the game and return an action among moving left, moving right, moving forward, moving backward, or attacking.
*   Keep a memory of explored positions and their values 
*   Update values of an explored position

The maze is a 20*20 square plain surrounded by lava. The goals are represented as diamonds. The goal can show up anywhere on the map. The agent must reach one of the diamonds in order to succeed. There are also trees as obstacles, which require the agent to either avoid them or destroy them. Up to 40% of the maze can be trees. 



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/CS-1750.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/CS-1750.png "image_tooltip")


_Figure 1. Example of Maze. Red: Lava, Brown: Tree, Blue: Goals, Grey: Agent_

When the agent reaches one of the diamonds or steps into the lava, the game restarts. 

**Evaluation Plan**

Quantitative evaluation

We would try Q-learning as our approach first. We will design multiple test cases with different difficulties, e.g. an easy maze without trees and only one goal, and a maze with layers of trees and multiple goals. Every move costs 1 point. Dropping into the lava costs 10000 points because it is the worst. Reaching the goal brings 10000 points as the reward. The agent can also cut a tree to explore a new path and this action costs 15 points. We might adjust these values while working on this project to get better performance. The baseline of our project is that the agent can find a goal without cutting a tree. The expected result is that the agent can find a goal with the least cost. If the way is blocked by trees and it takes more than 15 steps to circumvent the obstacles, then the agent should choose to cut down the tree. We may try Deep Q-learning if the performance of Q-learning is bad or the memory is not enough. 

Qualitative evaluation

We will monitor the values of positions with visualizations. The agent should recognize the view of the game and convert it into an understanding of the 2D map of the maze. The sanity check cases are mazes with at most 60 trees (15%), the agent should find the least cost path to reach a goal in a reasonable amount of time. A moonshot case is one with around 160 trees (40%) and multiple goals surrounded by layers of trees. 



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/CS-1751.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/CS-1751.png "image_tooltip")


<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/CS-1752.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/CS-1752.png "image_tooltip")


Figure 2. Sanity Check Case Example & Moonshot Case Example

**Goals**

Minimum goal: Build an agent that is able to successfully solve a maze that has a relatively easy difficulty with no obstacles.

*   Milestone 1: Design a working maze and build the framework for testing an agent within a maze.

*   Milestone 2: Perform learning in order to have the agent successfully solve the maze and reach the diamonds.

Realistic goal: Add difficulty to the maze by making the layout more complex and adding obstacles, such that the agent can destroy or avoid obstacles in order to solve the maze.

*   Milestone 1: Design working mazes that are of higher complexity with additional obstacles but that are still reasonable and possible to solve.

*   Milestone 2: Train the agent to succeed in solving the maze even with the additional complexity.

Ambitious goal: Find the lowest cost path through a difficult maze with many obstacles and multiple goals.

*   Milestone: Find the lowest cost path and goal in the maze.
