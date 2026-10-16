# Poverty Share Allocation

## Overview

This repository contains an analytical approach for allocating program targets across cities and municipalities based on their share of the total estimated poor population.

The method is intended to support evidence-based and needs-oriented resource allocation by distributing a predetermined program target proportionally according to poverty-related measures.

## Objectives

- Develop a transparent and reproducible method for allocating program targets based on poverty data.
- Ensure that areas with a larger share of the estimated poor population receive a proportionally larger share of the total target.
- Support planning, target-setting, and resource allocation decisions using quantitative evidence.
- Provide a basis for examining the geographic distribution of program coverage.

## Methodology

### Poverty-Share Allocation

The allocation method distributes a fixed total target across geographic areas according to each area's proportion of the aggregate poverty measure.

The allocation formula is:

$$
A_i = T \times \frac{P_i}{\sum_{j=1}^{n} P_j}
$$

Where:

- \(A_i\) = Allocated target for city/municipality \(i\)
- \(T\) = Total program target to be distributed
- \(P_i\) = Poverty measure for city/municipality \(i\)
- \(n\) = Total number of cities/municipalities included in the allocation
- \(\sum_{j=1}^{n} P_j\) = Aggregate poverty measure across all included areas

The poverty measure may refer to the estimated number of poor households or another explicitly defined poverty-related measure, depending on the analytical requirements and available data.

### Interpretation

Under this approach, each city's or municipality's allocation is proportional to its share of the aggregate poverty measure.

For example, if a municipality accounts for 5% of the total estimated poor households across all included municipalities, it receives 5% of the total target under the basic allocation formula.

### Allocation Considerations

The following considerations are relevant when implementing the method:

- **Data consistency:** Use comparable poverty measures across all geographic areas.
- **Geographic coverage:** Ensure that the areas included in the calculation correspond to the intended program coverage.
- **Rounding:** Adjust rounded allocations, when necessary, to ensure that the final allocations sum to the total target.
- **Program requirements:** Consider eligibility criteria, operational capacity, and other applicable program-specific constraints.
- **Validation:** Compare the resulting allocations with historical coverage, geographic poverty patterns, and other relevant indicators.

## Expected Outputs

Depending on the implementation, the analysis may produce:

- Poverty-share estimates for each city or municipality.
- Allocated program targets by geographic area.
- Geographic allocation summaries.
- Tables for reviewing and validating the distribution of targets.

## Applications

The poverty-share allocation method may be used to inform:

- Geographic distribution of social protection program targets.
- Local-level target-setting and planning.
- Assessment of the equity of proposed target allocations.
- Scenario analysis for alternative total program targets.

## Limitations

Poverty-share allocation is a proportional allocation method and does not, by itself, account for differences in program eligibility, implementation capacity, service delivery costs, or other dimensions of vulnerability.

Its results depend on the quality, coverage, and definition of the poverty measure used. Allocations should therefore be interpreted as a quantitative basis for planning rather than as an automatic determination of individual household eligibility.

## Repository Scope

This repository focuses on poverty-share-based allocation. The specific data inputs, processing procedures, implementation details, and outputs should be documented alongside the corresponding files in the repository.

