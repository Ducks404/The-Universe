### Can only generate successors and distinguish goal and nongoal

| Evaluation       | BFS | Uniform Cost | DFS | DLS           | IDS |
| ---------------- | --- | ------------ | --- | ------------- | --- |
| Time Complexity  | b^d | b^d          | b^m | b^l           | b^d |
| Space Complexity | b^d | b^d          | bm  | bl            | bd  |
| Completeness     | Yes | Yes          | No  | Yes if L >= D | Yes |
| Optimality       | Yes | Yes          | No  | No            | Yes |
## State Space Search
Two main approaches to searching a state space: 
### Data driven search 
> Forward Chaining

- Start -> Goal
- Goal is not clear or hard to formulate precisely.
- All or most of the data are given in the initial problem statement. 
- Large number of potential goals
### Goal driven search 
> Backward Chaining

- Goal -> Start
- Goal can be clearly and easily formulated, e.g., theorem prover; finding an exit path from a maze; medical diagnosis (with known conditions).
- Problem data are not given but must be acquired by the problem solver.

Both search the same state space and produce the same result, however the order and actual number of states searched can be different
## Tree Search vs Graph Search
### Tree
> Does not store closed/visited nodes
### Graph
> Stores closed/visited => no redundant nodes