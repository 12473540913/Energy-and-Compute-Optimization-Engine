# Energy and Compute Optimization Engine

An applied mathematics project for modeling and optimizing the scheduling of energy storage, electricity consumption, renewable generation, and flexible compute workloads under operational constraints and uncertainty.

## Project Goals

This project develops an optimization platform that will:

- Schedule grid electricity, renewable generation, battery charging, and battery discharging.
- Schedule flexible compute workloads subject to timing, energy, and operational constraints.
- Formulate the scheduling problem using linear programming (LP) and mixed-integer linear programming (MILP).
- Compare deterministic, stochastic, and robust optimization strategies.
- Evaluate strategies using simulated demand, electricity prices, renewable generation, and uncertainty.
- Visualize system behavior, optimization decisions, costs, and tradeoffs.

## Mathematical Themes

The project is intended as an applied study of:

- Linear programming
- Mixed-integer linear programming
- Constrained optimization
- Probability and uncertainty
- Numerical optimization
- Operations research
- Dynamic resource allocation
- Quantitative decision-making

A central structure throughout the project is:

\[
\min_x C(x)
\]

subject to system dynamics and operational constraints.

For the energy-storage system, the battery state evolves over time according to a discrete-time relationship of the general form

\[
E_{t+1}
=
E_t
+
\eta_c P_t^{charge}\Delta t
-
\frac{P_t^{discharge}\Delta t}{\eta_d}.
\]

This provides a useful introduction to optimization over dynamic systems.

## Planned Investigations

| # | Investigation | Purpose |
|---|---|---|
| 01 | Problem Formulation | Develop optimization fundamentals and formulate small constrained problems |
| 02 | Deterministic Optimization | Build the baseline energy and battery scheduling model |
| 03 | Stochastic Optimization | Incorporate uncertain demand, prices, and renewable generation |
| 04 | Robust Optimization | Optimize against bounded uncertainty and adverse scenarios |
| 05 | Strategy Comparison | Compare cost, risk, reliability, and robustness across approaches |

Additional investigations may be added as the project develops.

## Repository Structure

```text
Energy-and-Compute-Optimization-Engine/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── docs/
│   ├── mathematical_model.md
│   ├── assumptions.md
│   └── results.md
│
├── notebooks/
│   └── README.md
│
├── src/
│   ├── __init__.py
│   ├── data.py
│   ├── model.py
│   ├── scenarios.py
│   ├── solve.py
│   └── visualization.py
│
├── data/
│   └── README.md
│
├── results/
│   ├── deterministic/
│   ├── stochastic/
│   └── robust/
│
└── tests/
    ├── __init__.py
    ├── test_constraints.py
    └── test_energy_balance.py
```

## Technology

The initial implementation uses:

- Python
- Pyomo
- HiGHS
- NumPy
- pandas
- Matplotlib
- SciPy
- JupyterLab
- pytest

## Setup

Create and activate a Python virtual environment, then install the dependencies:

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

Install:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Launch JupyterLab:

```bash
jupyter lab
```

## Development Philosophy

The mathematical formulation comes before implementation.

Each major investigation proceeds through:

1. Define the physical or operational problem.
2. Identify parameters and assumptions.
3. Define decision variables.
4. Construct the objective function.
5. Derive constraints.
6. Predict expected optimizer behavior.
7. Implement the model.
8. Verify the solution.
9. Visualize and interpret results.
10. Document conclusions and limitations.

The objective is not merely to call an optimization solver, but to understand and justify the mathematical model being solved.
