# Poverty Share-Based Allocation of Program Targets

A data-driven approach to distributing program targets across local government units (LGUs) in the Philippines based on poverty shares and existing program coverage.

## Overview

This repository focuses on the computation of poverty-share-based program target allocations. It provides an analytical approach for estimating ideal targets for cities and municipalities, identifying gaps between ideal and existing targets, and distributing available additional slots according to residual need.

The approach is intended to support evidence-based target setting and promote a more equitable geographic distribution of program coverage.

## Allocation Methodology

The allocation process follows these steps:

1. Calculate each LGU's share of the selected poverty measure.
2. Estimate its ideal program target based on its poverty share.
3. Compare its ideal target with its current or projected target.
4. Calculate residual needs and the available additional slots.
5. Distribute additional slots proportionally according to residual need.
6. Calculate final target allocations and validate the results.

### Allocation Formula

The ideal target for LGU \(i\) is:

$$
I_i = T_{\text{nat}} \times
\frac{P_i}{\sum_{j=1}^{n} P_j}
$$

Where:

- $I_i$ = Ideal target for LGU $i$
- $T_{\text{nat}}$= National program target
- $P_i$ = Selected poverty measure for LGU $i$
- $n$ = Number of LGUs included in the allocation

Residual need is calculated as:

$$
R_i = \max(I_i-C_i,0)
$$

Where $C_i$ represents the current or projected target for LGU $i$.

The additional allocation is:

$$
U_i = \frac{R_i}{\sum_{j=1}^{n}R_j}\times A
$$

Where $A$ is the number of available additional slots.

The final target allocation is:

$$
F_i=C_i+U_i
$$

This method retains existing targets under the proposed no-reduction rule and distributes additional slots among LGUs with positive residual needs, provided the allocation constraints are feasible.

## Data Requirements

The analysis may require the following inputs, depending on the implementation:

- Geographic identifiers for cities and municipalities.
- Poverty measures used to calculate geographic poverty shares.
- Current or projected program targets by LGU.
- National program target.
- Expected beneficiary exits, where applicable.

The definitions, reference periods, and geographic coverage of the input data should be consistent across all included LGUs.

## Expected Outputs

Depending on the scripts and data-processing procedures implemented in this repository, outputs may include:

- Poverty shares by LGU.
- Ideal program targets.
- Residual needs and allocation weights.
- Additional slots allocated to each LGU.
- Final target allocations.
- Validation summaries for checking allocation totals and constraints.

## Important Considerations

- The poverty measure must be explicitly defined. Poverty incidence rates and estimated numbers of poor households can produce different allocation results.
- Existing targets should be reconciled with the national program target before applying the no-reduction rule.
- If no LGU has positive residual need, an alternative rule is required to distribute any remaining slots.
- Fractional allocations may require a documented rounding procedure to ensure that final allocations sum to the national target.
- The allocation of geographic targets does not automatically determine individual household eligibility.

## Repository Scope

This repository focuses on poverty-share-based target allocation. Its documented functionality should be interpreted according to the scripts, data inputs, and outputs actually included in the repository.

