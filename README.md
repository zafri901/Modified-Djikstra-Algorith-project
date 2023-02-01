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
Note: This code assumes that the input graph is represented as a dictionary where the keys are the nodes and the values are dictionaries of the neighboring nodes and their corresponding weights.

import heapq

def modified_dijkstra(graph, source, destination):
    distances = {node: float('inf') for node in graph}
    distances[source] = 0
    heap = [(0, source)]
    while heap:
        (curr_distance, curr_node) = heapq.heappop(heap)
        if curr_distance > distances[curr_node]:
            continue
        for neighbor, weight in graph[curr_node].items():
            if curr_distance + weight < distances[neighbor]:
                distances[neighbor] = curr_distance + weight
                heapq.heappush(heap, (distances[neighbor], neighbor))
    routes = []
    for node, distance in distances.items():
        if node == destination:
            route = [destination]
            curr_node = destination
            while curr_node != source:
                for neighbor, weight in graph[curr_node].items():
                    if distances[curr_node] - weight == distances[neighbor]:
                        route.insert(0, neighbor)
                        curr_node = neighbor
                        break
            routes.append(route)
    return routes

def calculate_probability(routes):
    probabilities = {}
    for route in routes:
        probability = 1
        for i in range(len(route) - 1):
            probability *= graph[route[i]][route[i + 1]]
        probabilities[tuple(route)] = probability
    return sorted(probabilities.items(), key=lambda x: x[1], reverse=True)

def calculate_runtime(routes):
    runtimes = {}
    for route in routes:
        runtime = 0
        for i in range(len(route) - 1):
            runtime += graph[route[i]][route[i + 1]]
        runtimes[tuple(route)] = runtime
    return sorted(runtimes.items(), key=lambda x: x[1])

graph = {
    'A': {'B': 0.7, 'C': 0.3},
    'B': {'C': 0.6, 'D': 0.4},
    'C': {'D': 0.9},
    'D': {}
}

routes = modified_dijkstra(graph, 'A', 'D')
probabilities = calculate_probability(routes)
for probability in probabilities:
    print('Route:', probability[0], 'Probability:', probability[1])

runtimes = calculate_runtime(routes)
for runtime in runtimes:
    print('Route:', runtime[0], 'Runtime:', runtime[1])





