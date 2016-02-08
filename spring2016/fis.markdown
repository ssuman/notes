## Intelligent Systems - 27 Jan

##### NOTE : Read chapter 1,2,3 from text book

#### Goals of AI

* Create an expert systems.
* To implement human intelligence into a machine.

#### UnInformed Search Strategies

BFS:
	* BFS has space constraints.
	* BFS also takes long time to complete once the depth increases.

Uniform Cost Search:

* Uniform Cost search uses the idea of BFS.
* Doesn't find the optimal path always.
* Will find the optimal path when g(successor(n)) > g(n)
* Negative cost will not work with this method.

DFS:
* Very modest memory requrirments.
* O(b^m) time complexity of DFS. where b is the braching factor and m is maximum depth.
* bm will be the storage requirements for DFS.
* Drawbacks -> it can get stuck going in the wrong path.
* Should be avoided when we have large trees with long depths.

Depth Limited Search:
* Uses DFS but imposes a cutoff on the maximum depth.

Iterative Deepening:
* Uses DFS limited search as a module to search.
* Initially the depth is set to 0. Gradually increased until the goal state is found.
* Time complexity is (d+1)b^0 + d b^1 + d-1 b^2 + d-2 b^3....+1 b^d  ----> o(b^d).
* When we have a large search space and depth of the solution is not known then use iterative deepening.

Bidirectional Search:
* Search both ways. This will make the depth to reduce in half. d/2. Hence the time complexity reduced to (b^(d/2)).
* Works well in theory but has lot of issues.
	* How to search backwards? Need a predecessor function.

#### Informed Search Strategies.

The idea is to use a evaluation function which tell which is the seemingly best next state. One of the way is to use

Greedy Search:
* One of the simplest best-first strategy is to minimize the estimated cost to reach the goal.
* A function that calculates such cost estimates is called Heuristic search.
* Search might never find the solution if the repeated states aren't identified.
* Its not optimal and its not complete. Time complexity is O(b^m).

A\* Search:
* Combine both F(n) = g(n) + h(n) where g(n) is uniform cost and h(n) is heuristic cost.
	* A\* is optimal and complete.

