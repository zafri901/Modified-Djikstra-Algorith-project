# Modified Djikstra Algorith Assignment


- CSCI 3302
- DATA STRUCTURES AND ALGORITHMS II SEMESTER I, 2022/23
- Student : Muhammad Nor Zafri Bin Ahmad ( 1913139 )
- Taken from : Design of a Modified Dijkstra’s Algorithm for finding alternate routes for shortest-path problems with huge costs (2020)
- Author : Omoniyi Ajoke Gbadamosi

| Contents |
| ------- |
| Abstract |
| Pseudocode |
| Performance |
| Advantage And Disadvantages |
| When to use which algorithm |
| Code | 


# Abstract

The classical Dijkstra’s algorithm has been 
widely used in shortest path problems. It is indeed one of the 
most referenced shortest path algorithms. However, it is 
observed that in certain circumstances finding shortest paths 
between given nodes may be achieved at a huge cost especially 
where time and efforts are of significant consideration. Such 
cases are the basic consideration in this study. Solution to such 
situations requires a modified Dijkstra’s algorithm, which is 
proposed in this study


# Pseudocode

| Steps | Pseudocode |
| --------- | ------- |
| Step 1 | Use the conventional Dijkstra’s algorithm to generate all the routes from a given source node i to the destination node j. |
| Step 2 | Calculate the probability of traversing from i to j through all the nodes between i and j |
| Step 3 | Output the result in descending order of probabilities |
| Step 4 | Consider traversing the routes starting with the route with the highest probability |
| Step 5 | Record the runtime of each route |
| Step 6 | Output the runtime in order of efficiency |
| Step 7 | Return.|

# Performance (time/space complexity or numerical experiment)

| O (E lg V) |
| --------- |

# Advantage And Disadvantages

| Advantage | Disadvantages |
| ------ | ------ |
| Can give alternative paths if the shortest path is not available. | Not efficient, will find all possible solutions and will take a long time to complete. |


# When to use which algorithm

Some occasions the shortest routes may not be available for use, in such a 
situation our study considers the use of alternate routes


# Code





