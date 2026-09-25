# Model Assumptions

This document records assumptions used throughout the Energy and Compute Optimization Engine.

Assumptions should be explicit, justified where possible, and revised as the model becomes more realistic.

## Time Representation

Initial models will use discrete time intervals.

Default starting assumption:

- Time step: 1 hour
- Optimization horizon: 24 hours

Later experiments may use longer horizons or finer time resolution.

## Electrical Demand

Initial demand profiles will be simulated rather than taken from a physical facility.

Starting assumptions:

- Demand is known exactly in the deterministic model.
- Demand is nonnegative.
- Demand must be satisfied during every time interval unless an explicit load-shedding mechanism is introduced.

Uncertainty will be added in later investigations.

## Grid Electricity

Starting assumptions:

- Grid electricity is available during all modeled time intervals.
- Electricity price may vary with time.
- Grid import is nonnegative.
- Export to the grid is initially disabled unless explicitly modeled later.

## Renewable Generation

Solar generation will be the initial renewable source.

Starting assumptions:

- Available solar generation is nonnegative.
- Solar generation may vary by time.
- Excess solar may be curtailed if it cannot be consumed or stored.
- Deterministic experiments initially assume solar availability is known.

Later experiments will introduce forecast uncertainty.

## Battery

The battery model will initially include:

- Finite energy capacity
- Maximum charging power
- Maximum discharging power
- Charging efficiency
- Discharging efficiency
- State-of-charge dynamics
- Initial state of charge

Potential later additions:

- Minimum state of charge
- Terminal state-of-charge requirements
- Cycling penalties
- Degradation costs
- Maximum cycle counts
- Self-discharge

## Compute Workloads

Flexible compute jobs may include:

- Energy or power requirements
- Runtime
- Earliest start time
- Deadline
- Interruptibility
- Priority

Binary decision variables may be introduced where jobs require discrete scheduling decisions.

## Uncertainty

Later investigations may model uncertainty in:

- Electrical demand
- Renewable generation
- Electricity price

Uncertainty models should state their assumed probability distributions, bounds, correlations, and scenario-generation procedures.

## Scope

The project is an optimization and applied mathematics investigation rather than a high-fidelity electrical-grid simulator.

Simplifications are acceptable when they are explicitly documented and appropriate to the mathematical question being studied.
