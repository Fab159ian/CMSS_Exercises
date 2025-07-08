
## Prerequisites

- Python 3.12 or higher
- pip package manager

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Fab159ian/CMSS_Exercises.git
cd CMSS_Exercises
```

2. Create a virtual environment (recommended):
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Exercise 1: Baronchelli et al. (2006) - Naming Game Replication

**File:** `exercise1.ipynb`  
**Group Size:** 2-person assignment  
**Paper:** "Sharp transition towards shared vocabularies in multi-agent systems"  
**Objective:** Faithful replication of vocabulary convergence in multi-agent systems

### Reproducing Results

1. Open `exercise1.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells sequentially (Cell → Run All)
3. The notebook will automatically:
   - Install required dependencies
   - Run the baseline Naming Game model
   - Generate Figure 2 (vocabulary evolution over time)
   - Generate Figure 3 (scaling behavior with population size)
   - Create additional histograms showing word distribution per agent

### Expected Outputs

- **Figure 2 replication:** Total words, unique words, and success rate over time
- **Figure 3 replication:** Characteristic times and maximum words vs population size
- **Additional analysis:** Histograms of word counts per agent at different success rates

### Key Parameters

- Population size: N = 1000 agents
- Number of objects: M = 1
- Simulation time: T = 100,000 steps
- Number of runs: 50 (reduced from paper's 3000 for performance)

## Exercise 2: Watts (2002) - Global Cascade Model Replication

**File:** `exercise2.ipynb`  
**Group Size:** 2-person assignment  
**Paper:** "A simple model of global cascades on random networks"  
**Objective:** Replication of threshold-based cascade dynamics in complex networks

### Reproducing Results

1. Open `exercise2.ipynb` in Jupyter Notebook
2. Run all cells sequentially
3. The notebook will:
   - Implement the Watts cascade model with threshold-based activation
   - Generate cascade size distributions for different network parameters
   - Analyze the "cascade window" phenomenon
   - Visualize network effects on cascade propagation

### Model Components

- **GraphAgent:** Agents with binary states (active/inactive) and individual thresholds
- **GraphModel:** Network-based simulation using Mesa and NetworkX
- **Threshold distributions:** Homogeneous, uniform, and normal distributions
- **Network generation:** Random graphs with controlled average degree

### Expected Outputs

- **Cascade size distributions:** Power law vs bimodal distributions
- **Cascade window analysis:** Effect of average degree on cascade probability
- **Network heterogeneity effects:** Impact of degree and threshold variability
- **Vulnerable cluster analysis:** Identification of cascade-triggering structures

### Key Parameters

- Network size: N = 1000 nodes
- Average degree: z = 2-10 (cascade window exploration)
- Threshold distributions: Uniform(0,1), Normal(μ,σ), Homogeneous(θ)
- Initial seed: 1% of nodes activated
- Simulation time: T = 100 steps

## Project: Miscommunication Extensions

**File:** `project.ipynb`  
**Group Size:** 4-person project  
**Objective:** Study the effects of various miscommunication mechanisms on vocabulary convergence

### Reproducing Results

1. Open `project.ipynb` in Jupyter Notebook
2. Run all cells sequentially
3. The notebook will:
   - Implement 8 different miscommunication types
   - Run comparative experiments
   - Generate comprehensive visualizations

### Miscommunication Types Implemented

1. **Noise-based:** Random character substitutions during transmission
2. **Selective Hearing:** Probabilistic word rejection
3. **Memory Decay:** Age-dependent vocabulary word removal
4. **Confirmation Bias:** Preference for vocabulary-similar words
5. **Cognitive Load:** Maximum vocabulary size constraints
6. **Partial Understanding:** Incomplete word retention
7. **Cultural Barriers:** Length-based word filtering
8. **Communication Delays:** Temporal transmission delays

### Expected Outputs

- **Comparative analysis:** Success rates, convergence times, and unique words for each miscommunication type
- **Visualization dashboard:** 4-panel comparison of key metrics
- **Detailed results:** Individual run data and aggregated statistics

### Key Parameters

- Population size: N = 500 agents
- Number of objects: M = 1
- Simulation time: T = 100,000 steps
- Number of runs: 5 per miscommunication type
- Baseline comparison included

## Dependencies

The following packages are required (see `requirements.txt`):

- `mesa>=3.0.0`: Agent-based modeling framework
- `numpy`: Numerical computations
- `pandas`: Data manipulation and analysis
- `matplotlib`: Basic plotting
- `seaborn`: Statistical visualizations
- `scipy`: Statistical functions and curve fitting
- `networkx`: Network analysis and graph generation

## Troubleshooting

### Common Issues

1. **Memory errors with large populations:**
   - Reduce `N` parameter in experiments
   - Use smaller `t` (simulation time)
   - Reduce number of runs

2. **Slow execution:**
   - The original papers used many more runs, we use fewer for performance
   - Reduce `data_resolution` parameter for less frequent data collection
   - Use smaller population sizes for testing

3. **Import errors:**
   - Ensure virtual environment is activated
   - Reinstall requirements: `pip install -r requirements.txt --force-reinstall`

## Citations

Papers replicated:

```bibtex
@article{baronchelli2006sharp,
  title={Sharp transition towards shared vocabularies in multi-agent systems},
  author={Baronchelli, Andrea and Felici, Maddalena and Loreto, Vittorio and Caglioti, Emanuele and Steels, Luc},
  journal={Journal of Statistical Mechanics: Theory and Experiment},
  volume={2006},
  number={06},
  pages={P06014},
  year={2006},
  publisher={IOP Publishing}
}

@article{watts2002simple,
  title={A simple model of global cascades on random networks},
  author={Watts, Duncan J},
  journal={Proceedings of the National Academy of Sciences},
  volume={99},
  number={9},
  pages={5766--5771},
  year={2002},
  publisher={National Acad Sciences}
}
```

---

**Note:** This implementation reproduces two seminal papers in complex systems and extends the Naming Game with various miscommunication mechanisms to study the robustness of vocabulary convergence under realistic communication constraints.