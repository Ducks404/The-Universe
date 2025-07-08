
| Classical                                  | Modern                                     |
| ------------------------------------------ | ------------------------------------------ |
| Search Tree:                               | Solution Encoding:                         |
| Partial solutions (nodes and edges)        | Complete solutions for problem             |
| Systematic Strategies (usually from local) | Operators involving local and global space |

## Local vs Global
### Local
- Start from one partial solution and explore **local neighbors** defined by search operators
### Global
- Start from multiple complete solutions
- Take solutions from the whole space and combine them to generate new solutions
- Avoid constraints to avoid local optima
- Example: [[Evolutionary Algorithms]]
