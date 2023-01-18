# Modified Djikstra Algorith Project


| Pseudocode |
| --------- |
| Step 1 Use the conventional Dijkstra’s algorithm to generate all the routes from a given source node i to the destination node j. 
Step 2 Calculate the probability of traversing from i to j through all the nodes between i and j 
Step 3 Output the result in descending order of probabilities 
Step 4 Consider traversing the routes starting with the route with the highest probability 
Step 5 Record the runtime of each route 
Step 6 Output the runtime in order of efficiency 
Step 7 Return.|

# Performance (time/space complexity or numerical experiment)

O (E lg V)

# Pros And Cons

| Advantage | Disadvantages |
| ------ | ------ |
| Can give alternative paths if the shortest path is not available. | Not efficient, will find all possible solutions and will take a long time to complete. |


# When to use which algorithm

Some occasions the shortest routes may not be available for use, in such a 
situation our study considers the use of alternate routes
