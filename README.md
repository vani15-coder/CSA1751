UCS IMPLEMENTATION
 

    while pq:
        cost, node, path = heapq.heappop(pq)

        if node in visited:
            continue
        visited.add(node)

        if node == goal:
            return cost, path

        for neighbor, weight in graph.get(node, []):
            if neighbor not in visited:
                heapq.heappush(
                    pq, (cost + weight, neighbor, path + [neighbor])
                )

    return float("inf"), []
BFS IMPLEMENTATION

    visited.add(start)

    while queue:
        node = queue.popleft()
        order.append(node)

        for neighbor in graph.get(node, []):
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)

    return order
DFS IMPLEMENTATION

    visited.add(start)
    order.append(start)

    for neighbor in graph.get(start, []):
        if neighbor not in visited:
            dfs(graph, neighbor, visited, order)

    return order
 A* IMPLEMENTATION


    mark node visited

    for each neighbor:
        new_g = g + cost
        new_f = new_g + heuristic(neighbor)
        push (new_f, new_g, neighbor)
GREEDY BEST FIRST SEARCH IMPLEMENTATION


    mark node visited

    for each neighbor:
        push (h(neighbor), neighbor)
MINMAX IMPLEMENTATION

    if isMax:
        best = -∞
        for each child:
            best = max(best, minimax(child, depth+1, False))
        return best
    else:
        best = +∞
        for each child:
            best = min(best, minimax(child, depth+1, True))
        return best
ALPHA BETA PRUNING IMPLEMENTATION

    if isMax:
        for each child:
            alpha = max(alpha, alphabeta(child, depth+1, alpha, beta, False))
            if alpha >= beta:
                break
        return alpha
    else:
        for each child:
            beta = min(beta, alphabeta(child, depth+1, alpha, beta, True))
            if beta <= alpha:
                break
        return beta
DESCISION TREE IMPLEMENTATION 
```
function predict(sample):
    node = root
    while node is not leaf:
        if sample satisfies condition:
            node = left_child
        else:
            node = right_child
    return node.label
```
NEURAL NETWORK CORE LOGIC
```
z = Σ(xi * wi) + bias
output = activation(z)
