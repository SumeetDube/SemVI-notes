

Simulated annealing is a probabilistic optimization algorithm inspired by the physical process of annealing in metallurgy. It's particularly useful for solving optimization problems where traditional methods may get stuck in local optima.

Here's a breakdown of how the simulated annealing algorithm works:

### Key Concepts:

1. **Objective Function**: Define the function \( f(x) \) that you want to minimize (or maximize) where \( x \) is the solution vector.

2. **Initial Solution**: Start with an initial solution \( x \) (could be randomly generated).

3. **Temperature Schedule**: Simulated annealing uses a temperature parameter \( T \) that controls the randomness in the search. This temperature decreases over time according to a predefined schedule.

### Algorithm Steps:

1. **Initialize**:
   - Choose an initial solution \( x_0 \).
   - Set an initial temperature \( T_0 \).
   - Choose cooling rate \( \alpha \) (how fast temperature decreases).

2. **Iterate**:
   - Repeat until stopping criterion (e.g., fixed number of iterations or temperature below a threshold):
     a. **Neighborhood Generation**:
        - Generate a neighboring solution \( x' \) by perturbing \( x \). This could involve small changes (like tweaking a parameter) or more complex transformations (like swapping or reordering).

     b. **Evaluate**:
        - Calculate the objective function \( f(x') \) for the new solution \( x' \).

     c. **Acceptance Probability**:
        - Compute the change in objective function \( \Delta f = f(x') - f(x) \).
        - If \( \Delta f < 0 \) (new solution is better), accept \( x' \) as the new solution.
        - If \( \Delta f \geq 0 \), accept \( x' \) with a probability \( e^{-\Delta f / T} \).
      
     d. **Update Solution**:
        - If \( x' \) is accepted, set \( x = x' \).

     e. **Cooling**:
        - Decrease the temperature \( T \) according to the cooling schedule (e.g., \( T = \alpha \times T \)).

### Temperature Schedule:

The choice of the cooling schedule is crucial:
- A common approach is exponential cooling: \( T_k = T_0 \times \alpha^k \), where \( T_k \) is the temperature at iteration \( k \).

### Key Parameters:

- **Initial Temperature \( T_0 \)**: Controls the initial level of randomness.
- **Cooling Rate \( \alpha \)**: Determines how fast the temperature decreases.
- **Acceptance Probability Function**: \( P = e^{-\Delta f / T} \), which decides whether to accept worse solutions based on the temperature.

### Stopping Criteria:

Typically, the algorithm terminates when the temperature falls below a predefined threshold or after a fixed number of iterations.

### Example Applications:

Simulated annealing can be applied to a wide range of optimization problems, including:
- Traveling Salesman Problem
- Job Scheduling
- Neural Network Training
- Graph Partitioning

### Benefits and Limitations:

- **Benefits**:
  - Can escape local optima by accepting worse solutions early in the search.
  - Does not require derivatives of the objective function.
  - Versatile and can handle complex objective functions.

- **Limitations**:
  - Sensitivity to the choice of temperature schedule and parameters.
  - Convergence properties can vary based on problem characteristics.
  - Can be computationally expensive for large problems.

Simulated annealing is a powerful technique for optimization problems where finding the global optimum is challenging due to the presence of many local optima. Its effectiveness often depends on fine-tuning the parameters and the choice of the cooling schedule.








----------------

SA is a metaheuristic optimization technique introduced by [Kirkpatrick et al.](https://www.dcs.gla.ac.uk/~pat/ads2/java/TxSxP/papers/sa.pdf "Kirkpatrick et al.") in 1983 to solve the [](https://www.baeldung.com/java-simulated-annealing-for-traveling-salesman#overview-2%20"travelling%20salesman%20problem") (TSP).

The SA algorithm is based on the [annealing process](https://en.wikipedia.org/wiki/Annealing_(materials_science) "annealing process") used in metallurgy, where a metal is heated to a high temperature quickly and then gradually cooled. At high temperatures, the atoms move fast, and when the temperature is reduced, their kinetic energy decreases as well. At the end of the annealing process, the atoms fall into a more ordered state, and the material is more ductile and easier to work with.

**Similarly, in SA, a search process starts with a high-energy state (an initial solution) and gradually lowers the temperature (a control parameter) until it reaches a state of minimum energy (the optimal solution).**

SA has been successfully applied to a wide range of optimization problems, such as TSP, [protein folding](https://en.wikipedia.org/wiki/Protein_structure_prediction "protein folding"), graph partitioning, and [job-shop scheduling](https://en.wikipedia.org/wiki/Job-shop_scheduling "job-shop scheduling"). **The main advantage of SA is its ability to escape from local minima and converge to a global minimum**. SA is also relatively easy to implement and does not require a priori knowledge of the search space.


## Algorithm[](https://www.baeldung.com/cs/simulated-annealing#algorithm)

The simulated annealing process starts with an initial solution and then iteratively improves the current solution by randomly perturbing it and accepting the perturbation with a certain probability. The probability of accepting a worse solution is initially high and gradually decreases as the number of iterations increases.

**The SA algorithm is quite simple, and it can be straightforwardly implemented as described below.**

### 3.1. Define the Problem[](https://www.baeldung.com/cs/simulated-annealing#1-define-the-problem)

First, we need to define the problem to optimize. **This involves defining the energy function, i.e., the function to minimize or maximize**. For example, if we want to minimize a real-valued function of two variables, e.g., ![f(x,y) = x^2 + y^2](x,y)%20=%20x^2%20+%20y^2)%20=%20x^2%20+%20y^2), the energy corresponds to the function ![f(x,y)](x,y))) itself. In the case of the TSP, the energy related to a sequence of cities is represented by the total length of the travel.

Once the energy function is defined, we need to set the initial temperature value and the initial candidate solution. The latter can be generated randomly or using some other heuristic method. Then we compute the energy of the initial candidate solution.

### 3.2. Define the Perturbation Function[](https://www.baeldung.com/cs/simulated-annealing#2-define-the-perturbation-function)

**A perturbation function is defined to generate new candidate solutions.** This function should generate solutions that are close to the current solution but not too similar. For example, if we want to minimize a function ![f(x,y)](x,y))), we can randomly perturb the current solution by adding a random value between -0.1 and 0.1 to both ![x](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-7e5fbfa0bbbd9f3051cd156a0f1b5e31_l3.svg "Rendered by QuickLaTeX.com") and ![y](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-38461fc041e953482219abf5d4cce1cb_l3.svg "Rendered by QuickLaTeX.com"). In the case of the TSP, a new candidate solution can be generated by swapping two cities in the traveling order of the current solution.

### **3.3. Acceptance Criterion**[](https://www.baeldung.com/cs/simulated-annealing#3-acceptance-criterion)

The acceptance criterion determines whether a new solution is accepted or rejected. The acceptance depends on the energy difference between the new solution and the current solution, as well as the current temperature. **The classic acceptance criterion of SA comes from statistical mechanics, and it is based on the** [Boltzmann probability distribution](https://en.wikipedia.org/wiki/Boltzmann_distribution "Boltzmann distribution"). A system in thermal equilibrium at temperature ![T](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-7e093fd43ad2c244140c11afe4d4bdff_l3.svg "Rendered by QuickLaTeX.com") can be found in a state with energy ![E](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-638a7387bd72763290cc777a9b509c38_l3.svg "Rendered by QuickLaTeX.com") with a probability proportional to ![\exp (-E / k T)](-E%20/%20k%20T)))

(1) ![\begin{equation*} \operatorname{Prob}(E) \sim \exp (-E / k T) \end{equation*}](E)%20%5Csim%20%5Cexp%20(-E%20/%20k%20T)%20%5Cend{equation*})%20%5Csim%20%5Cexp%20(-E%20/%20k%20T)%20%5Cend{equation*})

where ![k](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d42bc2203d6f76ad01b27ac9acc0bee1_l3.svg "Rendered by QuickLaTeX.com") is the [Boltzmann constant](https://en.wikipedia.org/wiki/Boltzmann_constant "Boltzmann constant"). Hence, at low temperatures, there is a small chance that the system is in a high-energy state. This plays a crucial role in SA because an increase in energy allows escape from local minima and find the global minimum.

**Based on the Boltzmann distribution, the following algorithm defines the criterion for accepting an energy variation ![\Delta E](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-845b0f70b748d7d0d3fbe1420e71d62a_l3.svg "Rendered by QuickLaTeX.com") at temperature ![T](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-7e093fd43ad2c244140c11afe4d4bdff_l3.svg "Rendered by QuickLaTeX.com").**

![Rendered by QuickLaTeX.com](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-9ee7bc6915ab17dc368f594f7b37d451_l3.svg "Rendered by QuickLaTeX.com")

A candidate solution with lower energy is always accepted. Conversely, a candidate solution with higher energy is acce pted randomly with probability ![\exp (- \Delta E / T)](-%20%5CDelta%20E%20/%20T))) (for our purpose, we can set ![k=1](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-fa9a164b15cd4025e77950a18cb40e4f_l3.svg "Rendered by QuickLaTeX.com")). The latter case can be implemented by comparing the probability with a random value generated in the range ![[0, 1)](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-1ccc107ad4e84ab8d43f0afb16345386_l3.svg "Rendered by QuickLaTeX.com").

### 3.4. Temperature Schedule[](https://www.baeldung.com/cs/simulated-annealing#4-temperature-schedule)

The temperature schedule determines how the temperature of the system changes over time. In the beginning, the temperature is high so that the algorithm can explore a wide range of solutions, even if they are worse than the current solution. As the iterations increase, the temperature gradually decreases, so the algorithm becomes more selective and accepts better solutions with higher probability. **A simple scheduling can be obtained by dividing the current temperature by a factor ![\alpha](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5f44d9bbc8046069be4aa2989bff19aa_l3.svg "Rendered by QuickLaTeX.com"), which is less than 1.**

### 3.5. Run the SA Algorithm[](https://www.baeldung.com/cs/simulated-annealing#5-run-the-sa-algorithm)

Finally, run the algorithm by iteratively applying the perturbation function and acceptance criterion to the current solution. The algorithm terminates when the temperature has cooled to a certain level ![T_{min}](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d82bca778e3b16bfb77922b41f4e30aa_l3.svg "Rendered by QuickLaTeX.com") or when the energy of the current solution is lower than a fixed threshold ![E_{th}](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-e4ad23e7daf9d0858014469723c4bb69_l3.svg "Rendered by QuickLaTeX.com").

**Here’s the pseudocode of SA:**

![Rendered by QuickLaTeX.com](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-2ee4ff077010e17983d05cabcdda1f27_l3.svg "Rendered by QuickLaTeX.com")

## 4. SA Flowchart[](https://www.baeldung.com/cs/simulated-annealing#sa-flowchart)

**Here, we provide a detailed flowchart representing all steps of SA:**

![simulated annealing flowchart](https://www.baeldung.com/wp-content/uploads/sites/4/2023/03/flowchart.png)

## 5. Example[](https://www.baeldung.com/cs/simulated-annealing#example)

To better understand the algorithm, we use SA to illustrate the minimization of the function ![f(x,y) = x^2 + y^2](x,y)%20=%20x^2%20+%20y^2)%20=%20x^2%20+%20y^2). We used as search space a grid of size 101 ![\times](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d79b8d6b331948a4e8f39f1af3358fdb_l3.svg "Rendered by QuickLaTeX.com") 101 placed in the square area defined by ![x,y)  \in [-10, 10](x,y)%20%20%5Cin%20[-10,%2010)(https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d7794c398612db28ece4b90d74b57fd3_l3.svg "Rendered by QuickLaTeX.com"|(x,y)  \in [-10, 10]]. We set the cooling rate ![\alpha=0.84](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d330aac514f763b27016b5fd49386400_l3.svg "Rendered by QuickLaTeX.com") and the initial solution ![(x,y)=(4,4)](x,y)=(4,4))=(4,4)). At each step, a new solution is generated by randomly shifting the current solution by ![\pm 0.2](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-2a934b987651889528fa1f89d391f1ac_l3.svg "Rendered by QuickLaTeX.com") in ![x](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-7e5fbfa0bbbd9f3051cd156a0f1b5e31_l3.svg "Rendered by QuickLaTeX.com") and ![y](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-38461fc041e953482219abf5d4cce1cb_l3.svg "Rendered by QuickLaTeX.com") direction.

**Here’s an animation showing the candidate solution, its energy, and the temperature at each step:**

![animation](https://www.baeldung.com/wp-content/uploads/sites/4/2023/03/animation.gif)

**We can observe that worse solutions are frequently accepted when the temperature is high. Conversely, when the temperature is low (e.g., ![T<1](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-8df1dc972207e4b1d15bd785cabd9907_l3.svg "Rendered by QuickLaTeX.com")), the algorithm is more selective, and better solutions are accepted with higher probability.**