# Genetic Algorithm for Function Optimization

## Overview
This project implements a Genetic Algorithm (GA) to optimize a given objective function. The algorithm encodes potential solutions as binary chromosomes, applies selection, crossover, and mutation operators, and evolves a population to minimize the function.

## Features
- **Binary Encoding**: Represents solutions as binary strings.
- **Tournament Selection**: Selects the best candidates for reproduction.
- **Crossover & Mutation**: Produces new solutions by combining parent chromosomes and applying mutations.
- **Objective Function Optimization**: Finds the minimum value of a given function.
- **Visualization**: Plots the function and traces the best solutions over iterations.

## Usage
1. Define an objective function to optimize.
2. Initialize the `GeneticAlgorithm` class with parameters such as chromosome length, population size, and mutation rate.
3. Run the algorithm and observe the best solution found.

### Example
```python
# Define an objective function
def sample_objective_function(x1, x2):
    return 1.5 - np.exp(-x1**2 - x2**2) - 0.5 * np.exp(-(x1 - 1)**2 - (x2 + 2)**2)

# Create and run the Genetic Algorithm
ga = GeneticAlgorithm(chromosome_length=20,
                      obj_func_num_args=2,
                      objective_function=sample_objective_function,
                      aoi=[-3, 3],
                      population_size=500,
                      tournament_size=2)

best_solution, best_value, trace, best_args = ga.run()
print("Best solution:", best_solution.array)
print("Decoded best solution (x,y):", best_args)
print("Value of the best solution:", best_value)
```

## Parameters
- `chromosome_length`: Number of bits in each chromosome.
- `obj_func_num_args`: Number of arguments for the objective function.
- `objective_function`: The function to optimize.
- `aoi`: The range of values for decoding the chromosome.
- `population_size`: Number of individuals in the population.
- `tournament_size`: Number of chromosomes competing in selection.
- `mutation_probability`: Probability of mutation per chromosome.
- `crossover_probability`: Probability of crossover occurring.
- `num_steps`: Number of generations to evolve.

## Output
- **Best Solution**: The binary chromosome with the lowest function value.
- **Decoded Best Solution**: The numerical representation of the best chromosome.
- **Best Value**: The function value of the best solution.
- **Visualization**: A contour plot showing the function and evolution trace.

---
Made by Anna Wierzbik

