# Mathematical Model

This document will contain the canonical mathematical formulation used by the project.

The formulation will evolve as the project progresses.

## Sets and Indices

Initial notation:

- \(t \in T\): discrete time interval
- \(j \in J\): flexible compute job
- \(s \in S\): uncertainty scenario

## Parameters

Candidate parameters include:

- \(c_t\): grid electricity price
- \(D_t\): electrical demand
- \(S_t\): available solar generation
- \(E_{\max}\): battery energy capacity
- \(P_{\max}^{charge}\): maximum battery charging power
- \(P_{\max}^{discharge}\): maximum battery discharging power
- \(\eta_c\): charging efficiency
- \(\eta_d\): discharging efficiency
- \(\Delta t\): duration of one time interval

Additional parameters will be introduced as compute scheduling and uncertainty are added.

## Decision Variables

Candidate decision variables include:

- \(P_t^{grid}\): grid power imported
- \(P_t^{charge}\): battery charging power
- \(P_t^{discharge}\): battery discharging power
- \(E_t\): battery stored energy
- \(P_t^{curtail}\): curtailed renewable power

Later MILP formulations may include binary variables associated with operating modes and compute scheduling.

## Objective Function

The initial deterministic objective will minimize electricity purchasing cost:

\[
\min \sum_{t \in T} c_t P_t^{grid}\Delta t.
\]

Later formulations may include:

- Battery degradation cost
- Compute scheduling penalties
- Curtailment penalties
- Reliability penalties
- Expected scenario cost
- Worst-case cost

## Energy Balance

A baseline power-balance relationship may take the form

\[
P_t^{grid}
+
P_t^{solar}
+
P_t^{discharge}
=
D_t
+
P_t^{charge}.
\]

The exact formulation will be revised when curtailment and compute loads are explicitly represented.

## Battery Dynamics

The battery state evolves according to

\[
E_{t+1}
=
E_t
+
\eta_c P_t^{charge}\Delta t
-
\frac{P_t^{discharge}\Delta t}{\eta_d}.
\]

## Battery Capacity

\[
0 \leq E_t \leq E_{\max}.
\]

## Charge and Discharge Limits

\[
0 \leq P_t^{charge} \leq P_{\max}^{charge}
\]

and

\[
0 \leq P_t^{discharge} \leq P_{\max}^{discharge}.
\]

## Mixed-Integer Decisions

Binary variables will be introduced only when a genuinely discrete decision must be represented.

Examples include:

- Starting a non-interruptible compute job
- Selecting mutually exclusive operating modes
- Enforcing logical scheduling constraints

## Deterministic Formulation

To be developed in Investigation 02.

## Stochastic Formulation

To be developed in Investigation 03.

## Robust Formulation

To be developed in Investigation 04.

## Verification

Every formulation should be checked for:

- Dimensional consistency
- Feasibility
- Correct variable bounds
- Correct sign conventions
- Boundary conditions
- Initial conditions
- Terminal conditions
- Physically impossible simultaneous actions
- Expected behavior in simple test cases
