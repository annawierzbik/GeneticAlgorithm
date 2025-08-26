# Genetic Algorithm Optimization Project

This project implements a **Genetic Algorithm (GA)** to optimize a test function of two variables

It allows experimentation with different GA parameters and visualizes both the search process and the final solutions.

---

## 🧬 Features

- Chromosome encoding as **bit strings**
- **Crossover** (one-point) and **mutation**
- **Tournament selection** for choosing parents
- Configurable GA parameters:
  - Chromosome length
  - Population size
  - Tournament size
  - Mutation probability
  - Crossover probability
  - Number of generations
- Function plotting with **GA search trace**
- Visualization of **best found solutions** on contour plots
- Comparison of multiple GA runs on a single plot

---

## ⚙️ How It Works

1. **Initialization**: Random population of chromosomes is generated.
2. **Decoding**: Each chromosome is decoded to real values in the search space.
3. **Evaluation**: Objective function is calculated for each individual.
4. **Selection**: Tournament selection chooses parents for reproduction.
5. **Crossover & Mutation**: Parents produce offspring using crossover and mutation.
6. **Replacement**: Offspring replace the old population.
7. **Iteration**: Steps 2–6 are repeated for a defined number of generations.
8. **Visualization**: Trace of the GA and final solutions are plotted on a contour plot.

---

## 🧪 Experiments

The notebook contains experiments that show how GA parameters affect the results:

1. **Chromosome length** – affects precision and search space size
2. **Population size** – affects diversity and convergence speed
3. **Tournament size** – affects selection pressure
4. **Mutation probability** – affects exploration vs. exploitation
5. **Crossover probability** – affects genetic recombination
6. **Number of generations** – affects convergence and refinement

For each experiment, the GA is run multiple times with different values, results are printed, and the **final best solutions** are plotted for comparison.

---

## 📊 Visualization

- **Search trace**: shows the path of GA through the search space.
- **Best solution marker**: the final best solution is highlighted on the contour plot.
- **Comparison plots**: final solutions from multiple runs can be displayed on one plot for easy comparison.

---

## 📌 Example Usage

```python
# Run GA with specific parameters
best_solution, best_value, trace, best_args = GeneticAlgorithm(
    chromosome_length=20,
    obj_func_num_args=2,
    objective_function=sample_objective_function,
    aoi=[-3, 3],
    population_size=200,
    tournament_size=2,
    mutation_probability=0.05,
    crossover_probability=0.8,
    num_steps=50
).run()

print("Best decoded solution (x,y):", best_args)
print("Value:", best_value)
