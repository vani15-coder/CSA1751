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
   A* Implementation 


    mark node visited

    for each neighbor:
        new_g = g + cost
        new_f = new_g + heuristic(neighbor)
        push (new_f, new_g, neighbor)
Greedy Best First Search (GBFS)


    mark node visited

    for each neighbor:
        push (h(neighbor), neighbor)
Minimax Algorithm
function minimax(node, depth, isMax):
    if node is leaf:
        return value

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
Alpha-Beta Pruning
function alphabeta(node, depth, alpha, beta, isMax):
    if node is leaf:
        return value

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
Decision Tree – Prediction Logic
start at root node\
while current node is not leaf:
    evaluate condition
    move to corresponding child

return class label
Entropy = 0
for each class:
    p = class_count / total
    Entropy -= p * log2(p)

Neural Network – Single Neuron
z = (x1*w1 + x2*w2 + ... + xn*wn) + bias
output = activation(z)
output = step(w1*x1 + w2*x2 + bias)

Single-layer perceptron fails for XOR

