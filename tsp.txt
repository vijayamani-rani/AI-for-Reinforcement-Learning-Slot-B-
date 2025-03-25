from itertools import permutations

def tsp(graph):
    n = len(graph)
    min_path = float('inf')
    min_route = []

    for perm in permutations(range(n)):
        current_cost = sum(graph[perm[i]][perm[i + 1]] for i in range(n - 1))
        current_cost += graph[perm[-1]][perm[0]]  # Return to starting point
        if current_cost < min_path:
            min_path = current_cost
            min_route = perm

    return min_path, min_route

graph = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0
