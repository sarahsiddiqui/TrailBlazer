# TrailBlazer
TrailBlazer is a city mapping software with a responsive UI that includes optimized directions, a search bar for specific roads, and buttons to display map landmarks. Integrated OpenStreetMap API for real-time data and solved the Traveling Salesman Problem using multi-threading and unordered maps in C++. Utilized the GTK graphics library for visualization.

NOTE: This project was made for the course ECE297 at the University of Toronto, and therefore, the source code is not available to the public.

## Main Features
* Use buttons to move around and zoom in/out with different map characteristics showing at each zoom level
* Dropdown menu to select maps for different cities
* Display streets, street names, parks, rivers, lakes, buildings, etc...
* Depending on the city, street names can be displayed in non-latin characters
* Customize displayed points of interest
* Search bar to search up intersections
* Find optimal path between two intersections using the Navigate Button
* Display easy-to-follow driving instructions to get from one point to another
* Dark Mode
* Help Box

## Algorithms
### Path Finding Algorithm
TrailBlazer utilizated the A* Search alogrithm to find the shortest path between two mapped intersections. Dijkstra’s Algorithm was initially used as a base to guarantee a fast solution. A* improves Dijkstra using an overhead time heuristic to find a route faster. The greedy approach was used to find the next, closest, legal intersection with the lowest time cost. Two-Opt was implemented to replace two pathways with each other to find a faster path iteratively where perturbations using simulated annealing was used to generate solutions and hill climb. Using this, a precomputed distance matrix for storing all pathway combinations for further use was created to ensure a responsive design.

Vectors were used to efficiently store features, points of interest, street segments, and intersections. These vectors are populated at the same time using multithreading resulting in high responsiveness.

### Traveling Salesman Problem
The Traveling Salesman Problem involves finding the shortest possible route that visits each city exactly once and returns to the starting point. This problem is computationally intensive due to the need to evaluate numerous potential routes, making it a classic example of an NP-hard problem where finding an exact solution quickly becomes impractical as the number of cities grows.

To solve the problem, our team utilized TrailBlazer, beginning with Dijkstra’s Algorithm to quickly determine initial shortest paths. We then enhanced this approach using the A* Search Algorithm to incorporate heuristics for faster route discovery. To refine the route further, we implemented a greedy strategy to choose the nearest, least costly intersections and applied the Two-Opt algorithm combined with simulated annealing for iterative optimization. This methodology allowed us to effectively address the TSP by continuously improving route accuracy and minimizing travel time.

