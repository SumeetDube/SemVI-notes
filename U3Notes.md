# Informed Vs Uninformed

| Parameters                 | Informed Search                                                                                                                                | Uninformed Search                                                                                                       |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Known as                   | It is also known as Heuristic Search.                                                                                                          | It is also known as Blind Search.                                                                                       |
| Using Knowledge            | It uses knowledge for the searching process.                                                                                                   | It doesn’t use knowledge for the searching process.                                                                     |
| Performance                | It finds a solution more quickly.                                                                                                              | It finds solution slow as compared to an informed search.                                                               |
| Completion                 | It may or may not be complete.                                                                                                                 | It is always complete.                                                                                                  |
| Cost Factor                | Cost is low.                                                                                                                                   | Cost is high.                                                                                                           |
| Time                       | It consumes less time because of quick searching.                                                                                              | It consumes moderate time because of slow searching.                                                                    |
| Direction                  | There is a direction given about the solution.                                                                                                 | No suggestion is given regarding the solution in it.                                                                    |
| Implementation             | It is less lengthy while implemented.                                                                                                          | It is more lengthy while implemented.                                                                                   |
| Efficiency                 | It is more efficient as efficiency takes into account cost and performance. The incurred cost is less and speed of finding solutions is quick. | It is comparatively less efficient as incurred cost is more and the speed of finding the Breadth-Firstsolution is slow. |
| Computational requirements | Computational requirements are lessened.                                                                                                       | Comparatively higher computational requirements.                                                                        |
| Size of search problems    | Having a wide scope in terms of handling large search problems.                                                                                | Solving a massive search task is challenging.                                                                           |
| Examples of Algorithms     | - Greedy Search<br>- A* Search<br>- AO* Search<br>- Hill Climbing Algorithm                                                                    | - Depth First Search (DFS)<br>- Breadth First Search (BFS)<br>- Branch and Bound                                        |
|                            |                                                                                                                                                |                                                                                                                         |
	 Heuristics search: hill climbing, branch and bound, best first search,
		Metaheuristics: Simulated annealing, Tabu search, ant colony optimization, real coded genetic algorithm.

# Heuristics 
**A heuristic is a strategy that uses information about the problem being solved to find promising solutions****.**

According to the chosen heuristic for a specific problem, the objective is not necessarily finding the optimal solution but only finding a good enough solution. Heuristics based on greedy search are in this class, for example.

Other times, we can use heuristics not to find a result but to discard obviously bad results. In such a case, heuristics remove portions of the search space and test all the remaining possible results. We call these heuristics supporting heuristics.

Regardless of which heuristic we adopt, they have some common characteristics:

- **Problem-based design**: heuristics are tailored to a particular problem. In this way, a single heuristic often can solve only one problem, and nothing more (one-to-one relation)
- **Non-measurable success**: different from approximate algorithms, heuristics don’t provide a clear indication of how close (or far) the obtained result is to the optimal one
- **Reasonable execution**: the time or computational resources for executing a heuristic must never exceed the requirements of any exact method that solves the same problem

The following image depicts how an exact, supporting heuristic and greedy search-based heuristic tackles a simple traveling salesman problem:

![Heuristics](https://www.baeldung.com/wp-content/uploads/sites/4/2022/08/Heuristics.png)
# Metahuristics

 metaheuristics aim to find promising results for a problem. **However, the algorithm used for a metaheuristic is generic and can deal with different problems.**

In this way, the characteristics of “non-measurable success” and “reasonable execution” are still the same as discussed for the heuristics. However, metaheuristics replace the principle of the problem-based design with the problem-independent design:

- **Problem-independent design**: the possibility of using the same metaheuristic algorithm to solve a myriad of problems by just tuning its inputs

Famous examples of metaheuristics are [](https://www.baeldung.com/cs/nature-inspired-algorithms#1-genetic-algorithm), [](https://www.baeldung.com/cs/nature-inspired-algorithms#2-particle-swarm-optimization), [](https://www.baeldung.com/java-simulated-annealing-for-traveling-salesman#overview-1), and variable neighborhood search. However, of course, [there exist many more](https://www.baeldung.com/cs/nature-inspired-algorithms).

Moreover, according to how a metaheuristic works to find results for a problem, we can divide them into three categories:

- **Local search metaheuristics**: also known as iterative improvement, metaheuristics in this category find a good final result by iteratively improving a single intermediate result
- **Constructive metaheuristics**: instead of solving entire problems at one time, constructive metaheuristics break a problem into multiple subproblems, solve each one of them and merge the partial results to provide a complete result
- **Population-based metaheuristics**: this category of metaheuristics considers a population of potential results for a given problem, thus improving these potential results by combining and modifying them

The following image shows a simple example of a traveling salesman problem being solved with a genetic algorithm, which is a population-based metaheuristic:

![Metaheuristics](https://www.baeldung.com/wp-content/uploads/sites/4/2022/08/Metaheuristics.png)

| **Aspect**         | **Heuristics**                                                                                                                       | **Metaheuristics**                                                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**     | Problem-solving methods that use practical experience and intuition to find a solution, often sacrificing optimality for efficiency. | Higher-level strategies designed to efficiently explore and exploit solution spaces to find good solutions within reasonable timeframes. |
| **Optimality**     | Generally do not guarantee optimal solutions.                                                                                        | Do not guarantee optimal solutions but often find good solutions in reasonable time.                                                     |
| **Scope**          | More specific and targeted towards particular types of problems or strategies.                                                       | More general and applicable across a wider range of problems and strategies.                                                             |
| **Algorithm Type** | Typically involve specific rules or techniques tailored for specific problem domains.                                                | More abstract and often involve guiding principles or frameworks applicable across different problems.                                   |
| **Complexity**     | Can be less complex and easier to implement for specific problems.                                                                   | Often more complex due to the need for sophisticated exploration and exploitation strategies.                                            |
| **Examples**       | Greedy algorithms, local search algorithms, construction heuristics.                                                                 | Genetic algorithms, simulated annealing, tabu search, ant colony optimization.                                                           |
|                    | hill climbing, branch and bound, best first search,                                                                                  | Simulated annealing, Tabu search, ant colony optimization, real coded genetic algorithm.                                                 |
|                    |                                                                                                                                      |                                                                                                                                          |
![quicklatex.com-448802b77022901f606d1f331ab5701c_l3 1](quicklatex.com-448802b77022901f606d1f331ab5701c_l3%201.svg)

## Heuristics
1. [Hill Climbing](Hill%20Climbing.md)
2. [branch and bound](branch%20and%20bound.md)
3. [best first search,](best%20first%20search,.md)

# Metaheuristics

[Simulated annealing](Simulated%20annealing.md)
[Tabu search](Tabu%20search.md)
[ant colony optimization](ant%20colony%20optimization.md)
[Real Coded Genetic Algorithm](Real%20Coded%20Genetic%20Algorithm.md)
