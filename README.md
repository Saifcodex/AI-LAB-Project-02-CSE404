# Topic Name : A* Search for Robot Navigation with Dynamic Costs
Theory : 
The A* search algorithm is one of the most efficient and popular algorithms used in pathfinding and graph traversal. It is widely used in artificial intelligence for navigating agents in grid-based environments.
Core Concepts:
A* uses a combination of actual cost (g) from the start node and a heuristic (h) to the goal node.


It chooses the path that minimizes:
                                                      f(n) = g(n) + h(n)
 where:
g(n) = cost to reach the node n from the start
h(n) = heuristic estimated cost to reach the goal from node n
Heuristic Used:
For this project, we use the Euclidean Distance:

Movement:
The robot can move in 8 directions: up, down, left, right, and diagonals.
Diagonal movement has a cost multiplier of 1.4 × terrain cost.

Motivation :
In warehouse robotics and autonomous logistics, robots must navigate efficiently through environments filled with dynamic terrains and obstacles. The navigation should:
Minimize travel cost
Avoid impassable obstacles
Consider terrain effects (like slippery or carpeted areas)
This project simulates a simplified grid-based warehouse where terrain costs vary, making it an ideal test case for A* search optimization.

Grid (Environment) :
Grid Size: 14 × 14
Obstacles: 10 impassable cells
Special Terrains: 6 cells with dynamic traversal costs
Start Point: (0, 0)
Goal Point: (13, 13)
![a_star_grid_with_all_fn_and_coords](https://github.com/user-attachments/assets/51b947d7-f361-4e5b-80fc-38602ecc6005)

Sample Input : 
14 14     # Grid dimensions
10           # Number of obstacle cells
2 2          # Coordinates of obstacles start
3 5
5 3
6 6
7 4
8 8
9 5
10 10
11 7
12 12    # Coordinates of obstacles end
6            # Number of terrain cost cells
1 1 2      #Coordinates and Terrain costs start
2 4 3
4 4 4
5 6 6
7 7 3
10 12 2  #Coordinates and Terrain costs start
0 0          # Starting cell
13 13      # Goal cell

Output : 
Path :  { (0, 0) , (1, 0) , (2, 1) , (3, 2) , (4, 3) , (5, 4) , (6, 5) , (7, 6) , (8, 7 ) , (9, 8) , (10, 9) , (11, 10) , (12, 11) , (13, 12) , (13, 13) }
Total Cost:  18.8

Discussion
The A* Search algorithm was applied to a 14×14 grid environment representing a warehouse with different terrain types and obstacles. The robot is designed to find the least-cost path from the starting cell to the goal cell. The environment included:
1. Obstacles, which are impassable.
2. Special terrain cells with higher movement costs.
3. Diagonal movement, which costs 1.4 times the base cost of the destination cell.
4. Euclidean distance as the heuristic function.
   
The f(n) value, which is the sum of the actual cost g(n) from the start to the current cell and the heuristic h(n) (estimated cost to the goal), was calculated for each visited cell. A full grid visualization was created, showing:
1. The f(n) value in each cell that was evaluated.
2. Obstacle locations.
3. Special terrain costs.
4. Start and Goal points.
5. Grid coordinates for better tracking.
The A* algorithm efficiently explored the environment and found an optimal path by balancing actual movement cost and heuristic guidance.

Conclusion
The implementation of the A* Search algorithm in a dynamic warehouse grid environment demonstrates its strength in pathfinding for intelligent robots. The robot successfully avoided obstacles and high-cost terrains to reach the goal with minimum cost. Key takeaways include:
1. A* is highly suitable for navigation tasks where terrain cost and heuristic estimates are important.
2. Visualizing f(n) values and terrain types helps understand the decision-making process of the robot.
3. The system can be extended to larger or more complex environments, or adapted for real-time dynamic updates.
   
This project showcases how AI techniques like A* can be practically applied to real-world problems such as robotic warehouse navigation.

