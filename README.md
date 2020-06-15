# AI_SurveillanceCameras

We implemented a program that finds the minimum number of cameras to cover all the cells in a room. It takes a text file that represents the map of a room as an input. We solved the problem Using Best-first search algorithms (Greedy search & A*) and Local search algorithms (Hill climbing & Simulated annealing).


1.Best-first search Algorithms:

i. Problem formulation:
Initial state: square matrix read from the file.
State: matrix. (map of the room with the cameras’ locations)
Actions: add camera.
Goal State : All blocks covered in the room with minimum number of cameras. Path Cost: number of cameras.

ii. The evaluation function:
Heuristic = empty blocks / max coverage. Cost = Number of camera.
f(n) for A* =Heuristic + Cost
f(n) for Greedy Search is the heuristic.


iii.Implementation:
Frontier is a priority queue.
Expanded set is a list.
State are Nodes with data matrix , heuristic , cost and Parent Node .
Calculate Max Coverage: putting camera in every possible place from the initial state and finding maximum coverage.
Calculating Heuristic: calculating the number of invisible blocks and dividing them on the maximum coverage.
Update Coverage: Eight for loops for every possible block a camera can cover, with conditions if any obstacle occurs it will break.


2.Local search algorithms:

i. Problem formulation:
Initial state: square matrix read from the file.
State: Matrix (map of the room with the cameras’ locations)
Actions: add camera and remove camera
Goal State : All blocks covered in the room with minimum number of cameras.
 
ii. Objective function: 
number of invisible blocks + number of cameras.(minimization)

iii.Implementation:

HillCliambing() method returns a solution for the given state by implementing hill climbing search which is a matrix (map of the room with the cameras’ locations). Moving to the next method in Hill climbing class which is choosBestNeighbor(LocNode), it takes a whole state and return the best found neighbor which is also a whole state not only a matrix.
SimulatedAnnealing method returns a solution for the given state by implementing Simulated Annealing search which is a matrix too same as hill climbing, this method change the temperature by a fixed cooling rate and we assign a temperature to start with. Moving to the next method in this class which is selectRandomNeighbor(LocNode) which take a whole state and return a random neighbor no matter if it’s the best or the worst. By applying the first method our choice will be associated with the temperature and the cooling rate and the probability of the bad moves will be high at the beginning.

Generate neighbors: In this method we took the current state from the parameter and we add one camera for all the possible position and we generated multiple states with an additional camera and we add these states to A Linked List, Also we called a removeOneCamera() which will generate a multiple states by deleting one camera for each different camera.
Choose random initial state: This method create the initial state by picking a random index and put a camera in that position.







