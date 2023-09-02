- **Metadata**
- [[Code]]
- Last Update: [[2020-07-03]]
- Summary: Cyclomatic complexity is a software metric used to indicate the complexity of a program. It is a quantitative measure of the number of linearly independent paths through a program's source code. 


- Definition
    - The cyclomatic complexity of a section of [source code](https://en.wikipedia.org/wiki/Source_code) is the number of linearly independent [paths](https://en.wikipedia.org/wiki/Path_(graph_theory) within it—where "linearly independent" means that each path has at least one edge that is not in one of the other paths
    - The nodes of the graph are indivisible groups of commands of a program and a directed edge connects two nodes if the second command might be executed immediately after the first command
    - CC might also be applied to individual functions, modules, methods, class etc.. as opposed to the whole source code
- Examples
    - ```javascript
a = 5
console.log(a)```
        - CC = 1
        - Why: No control flow statements
    - ```javascript
if(a == 5) {
              console.log("hit")
              } else {
                      console.log("default")
                      }```
        - CC = 2
        - Why: 2 possible code paths - one where `a == 5` and one where `a != 5`
- Complexity Equation 
    - `M = E - N + 2P`
        - `E = the number of edges of the graph`
        - `N = the number of nodes of the graph`
        - `P = the number of connected components`
            - Intuitively the number of regions which are connected components - i.e. which are subgraphs in which two or more vertices are connected to each other via paths
        - **This is only true if the program has one entry and one exit point** 
            - In this case the CC is equal to the number of "decision points" (if statements or conditional loops) 
