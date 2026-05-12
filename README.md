# Week 10 Coding #8: Haunted Hotel Sweep

## Summary

This assignment implements graph helper functions using adjacency lists, BFS, DFS, queues, stacks, and visited sets.

The graph represents hotel areas connected to neighboring areas.  
BFS (Breadth-First Search) explores the graph level by level using a queue.  
DFS (Depth-First Search) explores deeply into one path before backtracking using a stack.  
The `visited` set is important because it prevents infinite loops and repeated visits in graphs with cycles.

---

## Approach

- Used `graph.get(area, [])` to safely return neighbors even if the area is missing.
- Used BFS traversal to check whether a path exists between two areas.
- Implemented BFS using `collections.deque` as a queue.
- Implemented DFS using a list as a stack.
- Used a `visited` set in all traversals to avoid revisiting nodes.
- Used `reversed(graph[current])` in DFS so traversal order follows the original neighbor order.

---

## Complexity

### `get_neighbors`

- Time: `O(1)`
- Space: `O(1)`
- Why: Dictionary lookup takes constant time.

### `has_path`

- Time: `O(V + E)`
- Space: `O(V)`
- Why: BFS may visit every vertex and edge once.

### `bfs_order`

- Time: `O(V + E)`
- Space: `O(V)`
- Why: Every reachable node and edge is processed once.

### `dfs_order`

- Time: `O(V + E)`
- Space: `O(V)`
- Why: DFS may visit all vertices and edges once.

### Stretch: `count_reachable_areas`

- Time: `O(V + E)`
- Space: `O(V)`
- Why: BFS traversal checks all reachable vertices and edges.

---

## Edge-Case Checklist

- [x] empty graph
- [x] missing start area
- [x] missing target area
- [x] `start == target`
- [x] graph with a cycle
- [x] disconnected graph
- [x] area with no neighbors

Notes:

- Cycles were handled correctly by using a `visited` set.
- Missing areas return safe default values like `[]` or `False`.

---

## Tests Added

- Tested BFS traversal order on connected graphs.
- Tested DFS traversal order with cycles.
- Tested missing start and target areas.
- Tested disconnected graphs.
- Tested `start == target` case.
- Tested empty graph behavior.

---

## Known Limitations

```text
No known limitations.
```

---

## Assistance & Sources

AI used? Yes

If yes, explain what it helped with:

- explanations
- debugging
- syntax reminders
- complexity analysis
- markdown formatting

Other sources used:

- Python documentation for `collections.deque`
- Course lecture notes