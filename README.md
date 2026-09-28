# Randomized Optimization

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![mlrose_hiive](https://img.shields.io/badge/mlrose__hiive-RHC%20%7C%20SA%20%7C%20GA%20%7C%20MIMIC-4B8BBE)
![Keras](https://img.shields.io/badge/Keras-D00000?logo=keras&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-notebooks-F37626?logo=jupyter&logoColor=white)
![Course](https://img.shields.io/badge/Georgia%20Tech-CS%207641%20Machine%20Learning-B3A369)

Four randomized optimization algorithms compared on three classic problem domains, then three of them used to train a neural network without gradient descent. The study asks which search strategy suits which kind of fitness landscape, and what it costs, in fitness and in time, to replace backpropagation with a metaheuristic.

Built for CS 7641 Machine Learning at Georgia Tech. Follows on from the [supervised learning study](https://github.com/EdidiongA/Supervised-Machine-Learning), whose neural network is reused in Part 2.

---

## Contents

- [Overview](#overview)
- [Problem domains](#problem-domains)
- [Algorithms](#algorithms)
- [Project description](#project-description)
- [Getting started](#getting-started)
- [Repository structure](#repository-structure)
- [What each notebook covers](#what-each-notebook-covers)
- [References](#references)
- [Author](#author)
- [License](#license)

---

## Overview

| | |
|---|---|
| **Part 1** | Randomized hill climbing, simulated annealing, a genetic algorithm and MIMIC applied to Eight Queens, the Travelling Salesperson Problem and Four Peaks |
| **Part 2** | The neural network from the supervised learning study retrained with randomized hill climbing, simulated annealing and a genetic algorithm in place of gradient descent |
| **Library** | mlrose_hiive for the optimization problems and algorithms; Keras for the reference neural network |
| **Measurements** | Fitness over iterations, convergence, and wall-clock time per algorithm per problem |
| **Format** | Five Jupyter notebooks |

## Problem domains

| Problem | Type | What makes it interesting |
|---|---|---|
| Eight Queens | Discrete, constraint satisfaction | Many local optima close to the global one; tests how well each algorithm escapes near-solutions |
| Travelling Salesperson | Discrete, combinatorial | A large permutation space where crossover and neighbourhood structure matter |
| Four Peaks | Discrete, bit-string | A landscape designed with deceptive local optima that punish greedy search |

## Algorithms

| Algorithm | Search strategy | Strength |
|---|---|---|
| Randomized Hill Climbing | Local search with random restarts | Fast and simple; a baseline for the others |
| Simulated Annealing | Local search that accepts worse moves with a temperature-controlled probability | Escapes local optima early, then settles |
| Genetic Algorithm | Population search with selection, crossover and mutation | Recombines good partial solutions across a population |
| MIMIC | Estimation of distribution: models the structure of good solutions and samples from it | Exploits dependencies between variables; fewer evaluations at higher cost per iteration |

## Project description

In this project, machine learning techniques in randomized optimization are explored. In the first part of this project, three optimization problem domains (Eight Queens, Travelling Salesperson and Four Peaks) are created and applied to the randomized hill climbing, simulated annealing, genetic and MIMIC algorithms. In the second part of this project, the neural network implementation in the [Supervised Learning project](https://github.com/EdidiongA/Supervised-Machine-Learning) was reimplemented using the randomized hill climbing, simulated annealing and genetic algorithms from the [mlrose_hiive](https://github.com/hiive/mlrose) Python library.

## Getting started

### Requirements

Python 3.8 or later and Jupyter.

```bash
pip install numpy pandas matplotlib seaborn scikit-learn keras mlrose-hiive networkx python-chess ucimlrepo umap-learn jupyter
```

`mlrose_hiive` supplies the optimization problems, the four algorithms and the neural network weight-optimization wrapper. `networkx` supports the Travelling Salesperson graph and `python-chess` is used to display Eight Queens boards.

### Run the notebooks

```bash
jupyter notebook
```

Run Part 1 first, then Part 2. Each notebook runs top to bottom.

## Repository structure

```
.
├── README.md
├── Randomized_Optimization_Part_1.ipynb                                   # All four algorithms on all three problems, with analysis
├── Randomized_Optimization_Part_1_with_maximization_set_to_True.ipynb     # Part 1 rerun with the problems framed as maximisation
├── Randomized_Optimization_Part_1b.ipynb                                  # Analysis of Eight Queens and Four Peaks results
├── Randomized_Optimization_Part_2.ipynb                                   # Neural network trained with RHC, SA and GA
└── Randomized_Optimization_Part_2b.ipynb                                  # Weight search for the neural network with the three algorithms
```

## What each notebook covers

| Notebook | Contents |
|---|---|
| `Part_1` | Eight Queens, Travelling Salesperson and Four Peaks, each solved with randomized hill climbing, simulated annealing, a genetic algorithm and MIMIC, followed by analysis of the Four Peaks and Eight Queens results |
| `Part_1_with_maximization_set_to_True` | The same experiments with the problems configured as maximisation, for comparison |
| `Part_1b` | Standalone analysis of the Eight Queens and Four Peaks results |
| `Part_2` | The Keras neural network from the supervised study, then the same network trained through mlrose with randomized hill climbing, simulated annealing and a genetic algorithm |
| `Part_2b` | Using the three randomized algorithms to find weights for the neural network, with comparison to the reference |

## References

- Hayes, G. mlrose_hiive: Machine Learning, Randomized Optimization and SEarch. [GitHub](https://github.com/hiive/mlrose)
- De Bonet, J. S., Isbell, C. L. and Viola, P. (1997). MIMIC: Finding Optima by Estimating Probability Densities. *Advances in Neural Information Processing Systems 9.*
- Kirkpatrick, S., Gelatt, C. D. and Vecchi, M. P. (1983). Optimization by Simulated Annealing. *Science*, 220(4598).
- Mitchell, M. (1998). *An Introduction to Genetic Algorithms.* MIT Press.

## Author

**Edidiong-Abasi Anwanane**  
MSc Computer Science, Georgia Institute of Technology  
[Portfolio](https://edidionga.github.io) · [LinkedIn](https://www.linkedin.com/in/edidiong-abasi-anwanane/) · [GitHub](https://github.com/EdidiongA)

## License

MIT. See [LICENSE](LICENSE).
