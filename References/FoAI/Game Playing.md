> Introduces the idea of states changing from multiple agents

#### Why study game playing in AI:
- Games are intelligent activities 
- It is very easy to measure success or failure
- It doesn’t require large amounts of knowledge 
- Games were thought to be solvable by straightforward search from the starting state to a winning position

#### Games
> Specifically deterministic, turn-taking, two-player, zero-sum, perfect information


### MiniMax
> Algorithm applicable to adversarial games where both opponents play optimally
> If know starting position -> find if player that goes first wins, loses or both players draw

- Uses recursion to search game tree
- Has a **Utility function** which if:
	- Greater -> better for Max
	- Lesser -> better for Min
- Time complexity: O(b^d)

#### Process
1. Draw search tree
2. Set values for leaf node states, 1 for max, 0 for min
3. MAX's Turn: Take state with maximum utility
4. MIN's Turn: Take state with minimum utility

#### Optimization: Alpha Beta Pruning

- Alpha: best value along the path for MAX
- Beta: best value along the path for MIN
![[Pasted image 20250521175256.png]]

- Has to use DFS because values depend on next layer
- Use heuristics for best-first ordering of node expansion