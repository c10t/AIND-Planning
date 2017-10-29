# Heuristic Analysys

This is the results and analysis of planning searches
for the air cargo problems.

## Result - Problem 1

### Result metrics of run_search.py

| Search Function | Expansions | Goal Tests | New Nodes | Plan Length | Time Elapsed ( sec ) |
| --------------- | --- | --- | --- | --- | --- |
| breadth_first_search     | 43 | 56 | 180 | 6  | 0.038 |
| depth_first_graph_search | 12 | 13 | 48  | 12 | 0.009 |
| uniform_cost_search      | 55 | 57 | 224 | 6  | 0.042 |
| astar_search with h_pg_levelsum | 11 | 13 | 50 | 6 | 0.716 |
| astar_search with h_ignore_preconditions   | 41 | 43 | 170 | 6  | 0.037 |

### Optimal Path

```
Load(C1, P1, SFO)
Fly(P1, SFO, JFK)
Unload(C1, P1, JFK)
Load(C2, P2, JFK)
Fly(P2, JFK, SFO)
Unload(C2, P2, SFO)
```

## Result - Problem 2

### Result metrics of run_search.py

| Search Function | Expansions | Goal Tests | New Nodes | Plan Length | Time Elapsed ( sec ) |
| --------------- | --- | --- | --- | --- | --- |
| breadth_first_search     | 3346 | 4612 | 30534 | 9 | 12.211 |
| depth_first_graph_search | 1124 | 1125 | 10017 | 1085 | 7.286 |
| uniform_cost_search      | 4853 | 4855 | 44041 | 9  | 11.727 |
| astar_search with h_pg_levelsum | 86 | 88 | 841 | 9 | 44.239 |
| astar_search with h_ignore_preconditions   | 1450 | 1452 | 13303 | 9  | 3.711 |

### Optimal Path

```
Load(C3, P3, ATL)
Fly(P3, ATL, SFO)
Unload(C3, P3, SFO)
Load(C2, P2, JFK)
Fly(P2, JFK, SFO)
Unload(C2, P2, SFO)
Load(C1, P1, SFO)
Fly(P1, SFO, JFK)
Unload(C1, P1, JFK)
```

## Result - Problem 3

### Result metrics of run_search.py

| Search Function | Expansions | Goal Tests | New Nodes | Plan Length | Time Elapsed ( sec ) |
| --------------- | --- | --- | --- | --- | --- |
| breadth_first_search     | 14120 | 17673 | 124926 | 12 | 87.599 |
| depth_first_graph_search | 677 | 678 | 5608 | 660 | 3.671 |
| uniform_cost_search      | 18223 | 18225 | 159618 | 12  | 54.456 |
| astar_search with h_pg_levelsum | 325 | 327 | 3002 | 12 | 227.856 |
| astar_search with h_ignore_preconditions   | 5040 | 5042 | 44944 | 12  | 14.738 |

### Optimal Path

```
Load(C2, P2, JFK)
Fly(P2, JFK, ORD)
Load(C4, P2, ORD)
Fly(P2, ORD, SFO)
Unload(C4, P2, SFO)
Load(C1, P1, SFO)
Fly(P1, SFO, ATL)
Load(C3, P1, ATL)
Fly(P1, ATL, JFK)
Unload(C3, P1, JFK)
Unload(C2, P2, SFO)
Unload(C1, P1, JFK)
```

## Conclusion

The results shows A* Search with "ignore preconditions" heuristics
is the best solution to solve the air cargo problems
because it finds optimal path with the minimum time.

Depth First Search can find path very quickly
but the path is not optimal.

Breadth First Search and Uniform Cost Search are able to find optimal
path within 10 minutes, but they takes many time and space
(expansions, goal tests, and new nodes) as problems become complex.

A* Search with "level-sum" heuristics solve the problem with smaller
spaces but it is very slow.

In conclusion, it was not better using non-heuristic search planning
methods for all problems because non-heuristic simple searches
are sufficient to solve less complex problem like problem 1.
I suggest that using non-heuristic search planning at first
then consider heuristics when problems become more complex.

