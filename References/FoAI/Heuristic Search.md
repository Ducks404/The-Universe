### Has domain specific knowledge to decide best path to continue

### Heuristic Function *h(n)*
> Function that estimates the goodness of the node *n*
- Domain specific knowledge encoded inside of *h(n)*
- h(n) = 0 implies it is goal state
#### Admissibility
> *h(n) <= h\*(n)*
- Underestimates Node to Goal
#### Monotonicity
> *h(n) <= c(n,n') + h(n')*
> -> *f(n) <= f(n')*
- Underestimates Node to Neighbor
- Causes Path to always be not decreasing
- First process of node will always be optimal
#### Informedness
> if *h1(n) <= h2(n)* for all n & *h1(n)<h2(n)* for at least 1 n, h2 dominates h1
- Best efficiency -> Higher Vales but no over-estimation
#### Generating Heuristic
> Relaxed problems have lesser restriction on actions
- Cost of **optimal solution of relaxed** = **admissible heuristic of original**
#### Testing Heuristics
> Can be measured with Effective Branching Factor

## Best First Search

### [[Greedy Search]]
> *f(n) = h(n)*
### [[A* Search]]
> *f(n) = g(n) + h(n)*
- No loops/merges -> [[#Admissibility]] is enough
- Loops/merges -> Needs [[#Monotonicity]]
