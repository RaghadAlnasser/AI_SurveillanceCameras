# AI_SurveillanceCameras

We implemented a program that finds the minimum number of cameras to cover all the cells in a room. It takes a text file that represents the map of a room as an input. We solved the problem Using Best-first search algorithms (Greedy search & A*) and Local search algorithms (Hill climbing & Simulated annealing).


Best-first search Algorithms:

1. Problem formulation:
Initial state: square matrix read from the file.
State: matrix. (map of the room with the cameras’ locations)
Actions: add camera.
Goal State : All blocks covered in the room with minimum number of cameras. Path Cost: number of cameras.

2. The evaluation function:
Heuristic = empty blocks / max coverage. Cost = Number of camera.
f(n) for A* =Heuristic + Cost
f(n) for Greedy Search is the heuristic.


