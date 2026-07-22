# ADR1D and WQP-NM-Nutrients :droplet:

<div align="center">

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21499528.svg)](https://doi.org/10.5281/zenodo.21499528) [![GitHub](https://img.shields.io/badge/GitHub-gstinoco%2FADR1D-181717.svg?logo=github)](https://github.com/gstinoco/ADR1D) [![Data: CSV](https://img.shields.io/badge/Data-6%20CSV%20files-1F6F8B.svg)](data_processed/) [![ADR1D](https://img.shields.io/badge/ADR1D-v1.0.0-2E8B57.svg)](#books-adr1d-scientific-model) [![WQP snapshot](https://img.shields.io/badge/WQP%20snapshot-2026--07--14-3B6EA8.svg)](https://www.waterqualitydata.us/) [![Validation](https://img.shields.io/badge/Validation-passed-2E8B57.svg)](#white_check_mark-validation--quality-control) [![ADR1D license: CC BY 4.0](https://img.shields.io/badge/ADR1D%20license-CC%20BY%204.0-D4AF37.svg)](LICENSE)

**A reproducible analytical benchmark for one-dimensional contaminant transport, accompanied by a provenance-preserving snapshot of public water-quality observations.**

*Controlled transport physics and traceable environmental records in a compact, text-native release.*

### :link: Quick Links

[![Repository](https://img.shields.io/badge/Code-Repository-181717?logo=github)](https://github.com/gstinoco/ADR1D) [![Overview](https://img.shields.io/badge/Overview-Start-2E8B57)](#star2-overview) [![Data](https://img.shields.io/badge/Data-Structure-1F6F8B)](#open_file_folder-repository-structure) [![Model](https://img.shields.io/badge/ADR1D-Model-6F42C1)](#books-adr1d-scientific-model) [![WQP](https://img.shields.io/badge/WQP-Observations-3B6EA8)](#ocean-wqp-observational-component) [![Validation](https://img.shields.io/badge/Quality-Validation-2E8B57)](#white_check_mark-validation--quality-control) [![Citation](https://img.shields.io/badge/Use-Citation-7B5B3A)](#memo-how-to-cite) [![Team](https://img.shields.io/badge/People-Research%20Team-1F6F8B)](#scientist-research-team) [![Partners](https://img.shields.io/badge/Partners-Innovation-0B1B3A)](#factory-industry-partners-supporting-innovation) [![Contact](https://img.shields.io/badge/Support-Contact-3B6EA8)](#email-contact--support)

</div>

---

## :clipboard: Table of Contents

- [Overview](#star2-overview)
- [Repository Structure](#open_file_folder-repository-structure)
- [ADR1D Scientific Model](#books-adr1d-scientific-model)
- [ADR1D Generation Methodology](#gear-adr1d-generation-methodology)
- [ADR1D Data Dictionary](#file_cabinet-adr1d-data-dictionary)
- [ADR1D Partitions and Leakage Prevention](#twisted_rightwards_arrows-adr1d-partitions-and-leakage-prevention)
- [ADR1D Quick Start](#rocket-adr1d-quick-start)
- [Validation and Quality Control](#white_check_mark-validation--quality-control)
- [Release Identity](#lock-release-identity)
- [ADR1D Intended Uses](#dart-adr1d-intended-uses)
- [ADR1D Limitations](#warning-adr1d-limitations-and-out-of-scope-uses)
- [WQP Observational Component](#ocean-wqp-observational-component)
- [How to Cite](#memo-how-to-cite)
- [Scientific References](#books-scientific-references)
- [Research Team](#scientist-research-team)
- [Industry Partners](#factory-industry-partners-supporting-innovation)
- [License and Rights](#page_facing_up-license--rights)
- [Acknowledgments](#pray-acknowledgments)
- [Contact and Support](#email-contact--support)
- [FAQ](#speech_balloon-faq)

---

## :star2: Overview

This data release contains two separate and complementary components for
data-driven studies of contaminant transport and water quality:

- `ADR1D` is a synthetic one-dimensional benchmark with complete transport
  parameters, analytical space-time concentration fields, and noisy virtual
  sensors.
- `WQP-NM-Nutrients` is a curated snapshot of publicly accessible nutrient
  observations from streams in New Mexico, retrieved from the Water Quality
  Portal (WQP).

ADR1D supports controlled forward, inverse, reconstruction, and early-arrival
experiments. WQP-NM-Nutrients provides environmental observations with source,
organization, analytical-method, qualification, and station metadata. The two
components are not samples from the same system and must not be concatenated as
if they shared a physical or statistical population.

### :wrench: Key Capabilities

- **Controlled benchmarking:** analytical concentration fields and complete
  physical parameters for every ADR1D scenario.
- **Leakage-aware evaluation:** fixed train, validation, and test partitions at
  scenario level.
- **Observation realism:** noisy virtual sensors with documented random seeds.
- **Environmental context:** WQP records with provider, organization, method,
  qualification, and monitoring-location metadata.
- **Auditability:** plain-text tables, exact retrieval filters, processing
  decisions, validation results, and versioned release metadata.

> **Release:** ADR1D version `1.0.0` and the WQP snapshot were generated or
> curated and validated before publication. Component-specific rights and WQP
> attribution are documented below.

### :bar_chart: Package at a Glance

| Component | Scope | Main records |
|---|---|---:|
| `ADR1D` | Synthetic analytical transport benchmark | 300 scenarios |
| ADR1D field | 51 positions by 49 times per scenario | 749,700 rows |
| ADR1D sensors | 6 sensors by 49 times per scenario | 88,200 rows |
| `WQP-NM-Nutrients` | New Mexico stream nutrients, query window 2022-2026 | 9,932 observations |
| WQP numeric subset | Numeric, unit-bearing, uncensored results | 5,360 rows |
| WQP stations | Locations used by the observations | 342 stations |
| WQP provenance | NWIS and STORET records | 15 organizations |
| Format | Comma-separated text with header rows | 6 CSV files |

### :calendar: Release Chronology

| Item | Date |
|---|---|
| Scheduled development period | December 1-31, 2024 |
| Initial public repository release | July 20, 2026 |
| Last documentation update | July 2026 |

The scheduled development period and the public release record describe
different stages of the project. Retrieval, validation, repository, and
citation dates retain the dates on which those operations actually occurred.

---

## :open_file_folder: Repository Structure

```text
.
|-- README.md
|-- CITATION.cff
|-- LICENSE
|-- data_processed/
|   |-- synthetic_adr1d_scenarios.csv
|   |-- synthetic_adr1d_field.csv
|   |-- synthetic_adr1d_sensor_observations.csv
|   |-- wqp_nm_stream_nutrients_2022_2026_observations.csv
|   |-- wqp_nm_stream_nutrients_2022_2026_model_ready.csv
|   `-- wqp_nm_stream_nutrients_2022_2026_stations.csv
`-- docs/
    `-- team/
        |-- gtinoco.webp
        |-- dmota.webp
        |-- jagt.webp
        |-- gpj.webp
        |-- eci.webp
        |-- jlgf.webp
        |-- cnmb.webp
        `-- mgfl.webp
```

The three ADR1D files form one relational dataset:

- `synthetic_adr1d_scenarios.csv` is the parent table, with one row per
  physical scenario.
- `synthetic_adr1d_field.csv` contains 2,499 analytical values per scenario
  (51 spatial positions by 49 times).
- `synthetic_adr1d_sensor_observations.csv` contains 294 observations per
  scenario (6 sensors by 49 times).

Use `scenario_id` to join the tables. The `split` column is repeated in all
three files for convenience and is constant within each scenario.

The three WQP files form a second relational component:

- `wqp_nm_stream_nutrients_2022_2026_observations.csv` preserves all 9,932
  processed results, including censored and nonnumeric records.
- `wqp_nm_stream_nutrients_2022_2026_model_ready.csv` is a first-stage subset
  of 5,360 numeric, unit-bearing, uncensored results.
- `wqp_nm_stream_nutrients_2022_2026_stations.csv` contains the 342 monitoring
  locations used by the observations.

Use `monitoring_location_id` to join WQP observations to stations. The
`model_ready` table is a subset of `observations`, not an independent table.

This repository is a data-focused distribution. The equations, sampling rules,
random seeds, WQP queries, processing rules, variable definitions, validation
results, and rights notices needed to audit the release are documented below.

---

## :books: ADR1D Scientific Model

### Governing equation

ADR1D represents transport in a homogeneous one-dimensional medium with
constant parameters within each scenario:

$$
R\frac{\partial C}{\partial t}
=D\frac{\partial^2 C}{\partial x^2}
-v\frac{\partial C}{\partial x}
-\lambda R C.
$$

| Symbol | Meaning | Unit |
|---|---|---|
| $C(x,t)$ | Dissolved concentration | mg L<sup>-1</sup> |
| $x$ | Distance from the inlet | m |
| $t$ | Elapsed time | s |
| $v$ | Effective advective velocity | m s<sup>-1</sup> |
| $D$ | Longitudinal hydrodynamic dispersion coefficient | m<sup>2</sup> s<sup>-1</sup> |
| $R$ | Linear equilibrium retardation factor | dimensionless |
| $\lambda$ | First-order decay coefficient | s<sup>-1</sup> |

The initial condition is

$$
C(x,0)=0.
$$

At the inlet, a rectangular concentration pulse is prescribed:

```math
C(0,t)=C_0\mathbf{1}_{[t_0,t_0+\tau)}(t).
```

where $C_0$ is the source concentration, $t_0$ is the pulse start time, and
$\tau$ is its duration. The indicator equals one while the source pulse is
active and zero otherwise. The far-field condition is

$$
\lim_{x\rightarrow\infty}C(x,t)=0.
$$

The model therefore represents a semi-infinite domain. The interval from 0 to
1,000 m in the files is an observation window, not a finite domain with an
outlet boundary at 1,000 m.

### Analytical reference solution

The concentration field is evaluated with a reactive extension of the
Ogata-Banks step response [1]. Define

$$
u=\sqrt{v^2+4\lambda R D}.
$$

For $t>0$, the response to a unit step at the inlet is

$$
\begin{aligned}
S(x,t)={}&\frac{1}{2}
\exp\!\left(\frac{(v-u)x}{2D}\right)
\mathrm{erfc}\!\left(
\frac{Rx-ut}{2\sqrt{DRt}}
\right)\\
&+\frac{1}{2}
\exp\!\left(\frac{(v+u)x}{2D}\right)
\mathrm{erfc}\!\left(
\frac{Rx+ut}{2\sqrt{DRt}}
\right),
\end{aligned}
$$

with $S(x,t)=0$ for $t\leq0$. Linearity permits a finite pulse to be written as
the difference between two step responses:

$$
C(x,t)=C_0\left[S(x,t-t_0)-S(x,t-t_0-\tau)\right].
$$

At $x=0$, the prescribed pulse is imposed directly. This analytical
construction avoids attaching the reference labels to a particular numerical
mesh, time integrator, or truncation error.

Ogata and Banks [1] provide the classical semi-infinite longitudinal-dispersion
solution. Chen and Liu [2] are cited as a complementary analytical treatment of
one-dimensional transport with linear equilibrium sorption, first-order decay,
and time-dependent inlet conditions. ADR1D uses the explicit semi-infinite
response stated above; it does not use the finite-domain integral solution from
Chen and Liu.

## :gear: ADR1D Generation Methodology

The processed release was produced in six deterministic stages:

1. Construct a separate Latin hypercube for each transport regime.
2. Map unit-hypercube coordinates to the physical parameter ranges and impose
   the neutral values for inactive retardation or decay.
3. Derive dispersivity, dimensionless numbers, travel time, and pulse end time.
4. Assign complete scenarios to stratified training, validation, and test
   partitions.
5. Evaluate the analytical pulse response on the field grid and at the six
   virtual sensors.
6. Add seeded sensor noise, apply the reporting-limit rule, serialize the three
   CSV tables, and run structural and physical validation.

### Transport regimes

The benchmark contains 75 scenarios in each of four regimes. Inactive effects
are fixed exactly at their neutral values.

| Regime | Retardation factor $R$ | Decay coefficient $\lambda$ | Train | Validation | Test |
|---|---:|---:|---:|---:|---:|
| `conservative` | 1 | 0 | 53 | 11 | 11 |
| `decay_only` | 1 | sampled, &gt;0 | 53 | 11 | 11 |
| `retardation_only` | sampled, &gt;1 | 0 | 52 | 12 | 11 |
| `retardation_and_decay` | sampled, &gt;1 | sampled, &gt;0 | 52 | 11 | 12 |
| **Total** |  |  | **210** | **45** | **45** |

### Parameter design

Within each regime, seven continuous dimensions were sampled with a 75-point
Latin hypercube design [3]. Each dimension was divided into 75 equiprobable
strata, one uniformly jittered value was drawn from every stratum, and the
values were independently shuffled before the dimensions were combined.

| Parameter | Symbol | Design range | Scale |
|---|---|---:|---|
| Advective velocity | $v$ | 0.05-0.35 m s<sup>-1</sup> | linear |
| Dispersion coefficient | $D$ | 1-20 m<sup>2</sup> s<sup>-1</sup> | logarithmic |
| Retardation factor, when active | $R$ | 1.1-3.0 | linear |
| Decay coefficient, when active | $\lambda$ | 10<sup>-7</sup>-2&times;10<sup>-5</sup> s<sup>-1</sup> | logarithmic |
| Source concentration | $C_0$ | 0.2-5.0 mg L<sup>-1</sup> | logarithmic |
| Pulse start time | $t_0$ | 0-3,600 s | linear |
| Pulse duration | $\tau$ | 1,800-10,800 s | linear |

Because Latin-hypercube values are jittered within open strata, the nominal
design bounds are generally not attained exactly. The realized ranges in
version `1.0.0` are:

| Quantity | Minimum | Maximum |
|---|---:|---:|
| `velocity_m_s` | 0.0502795 | 0.349056 |
| `dispersion_m2_s` | 1.00072 | 19.8959 |
| `retardation_factor` | 1 | 2.99246 |
| `decay_rate_s_1` | 0 | 1.98670&times;10<sup>-5</sup> |
| `source_concentration_mg_L` | 0.200193 | 4.99548 |
| `source_start_s` | 9.27389 | 3,590.29 |
| `source_duration_s` | 1,870.87 | 10,793.29 |
| `dispersivity_m` | 3.25712 | 303.427 |
| `peclet_number` | 3.29568 | 307.019 |
| `damkohler_number` | 0 | 0.416173 |
| `advective_travel_time_s` | 2,869.31 | 50,211.5 |

The deterministic parameter and partition seed is `20260714`. Sampling was
implemented with Python's standard `random` module; no external sampling
library was used. Floating-point outputs were serialized with 12 significant
digits.

Four derived quantities are included in the scenario table:

$$
\alpha=\frac{D}{v},\qquad
\mathrm{Pe}=\frac{vL}{D},\qquad
\mathrm{Da}=\frac{\lambda R L}{v},\qquad
t_{\mathrm{adv}}=\frac{RL}{v},
$$

where $L=1{,}000$ m is the sampled length, $\alpha$ is dispersivity,
$\mathrm{Pe}$ is the domain Péclet number, $\mathrm{Da}$ is an advective
Damköhler number, and $t_{\mathrm{adv}}$ is the retarded advective travel time
over $L$.

### Space-time output grid

The analytical solution is evaluated at 51 uniformly spaced positions from 0
to 1,000 m ($\Delta x=20$ m) and 49 uniformly spaced times from 0 to 86,400 s
($\Delta t=1{,}800$ s). These coordinates are output locations only; they are
not nodes of a numerical solver.

### Virtual-sensor model

Six fixed sensors are evaluated analytically at every one of the 49 output
times:

| Sensor | Position (m) |
|---|---:|
| `S01` | 100 |
| `S02` | 250 |
| `S03` | 400 |
| `S04` | 600 |
| `S05` | 800 |
| `S06` | 1,000 |

Sensor values are evaluated directly from the analytical solution, not
interpolated from `synthetic_adr1d_field.csv`. This distinction matters for
`S02` at 250 m, which does not coincide with the 20 m field spacing.

For a true concentration $C_{\mathrm{true}}$, independent Gaussian noise is
generated with

$$
\epsilon\sim\mathcal{N}(0,\sigma^2),\qquad
\sigma=\max\left(0.002,\,0.03C_{\mathrm{true}}\right)
\ \text{mg L}^{-1}.
$$

The noisy value is first constrained to be nonnegative:

$$
C_{\mathrm{raw}}=\max(0,C_{\mathrm{true}}+\epsilon).
$$

A synthetic detection limit of 0.01 mg L<sup>-1</sup> is then applied. If
$C_{\mathrm{raw}}<0.01$ mg L<sup>-1</sup>, the reported concentration is 0.005 mg
L<sup>-1</sup> and `is_below_detection_limit=true`; otherwise the reported value is
$C_{\mathrm{raw}}$. The independent noise seed is `20260715`.

Overall, 73,405 of 88,200 observations (83.23%) fall below the synthetic
detection limit. This high proportion is expected because the complete time
window includes periods before plume arrival and after pulse passage. It must
be considered when designing regression, classification, or early-warning
experiments. No scenario is fully censored: the number of reported detections
per scenario ranges from 9 to 221, with a median of 40.

## :file_cabinet: ADR1D Data Dictionary

All files are comma-separated UTF-8 text with a header row and a period as the
decimal separator. Every listed field is required. The release contains no
blank data cells and uses no missing-value sentinel codes. Boolean values are
stored as lowercase `true` and `false`.

### `synthetic_adr1d_scenarios.csv`

One row describes one complete physical scenario.

| Column | Type | Unit | Description |
|---|---|---|---|
| `scenario_id` | string | - | Stable identifier, from `ADR1D-0001` to `ADR1D-0300`. |
| `split` | category | - | Scenario-level partition: `train`, `validation`, or `test`. |
| `regime` | category | - | `conservative`, `decay_only`, `retardation_only`, or `retardation_and_decay`. |
| `domain_length_m` | numeric | m | Length of the sampled interval. |
| `spatial_nodes` | integer | - | Number of sampled spatial coordinates. |
| `spatial_step_m` | numeric | m | Distance between adjacent field coordinates. |
| `final_time_s` | numeric | s | End of the sampled time window. |
| `time_nodes` | integer | - | Number of sampled times. |
| `time_step_s` | numeric | s | Time between adjacent outputs. |
| `velocity_m_s` | numeric | m s<sup>-1</sup> | Effective advective velocity $v$. |
| `dispersion_m2_s` | numeric | m<sup>2</sup> s<sup>-1</sup> | Longitudinal dispersion coefficient $D$. |
| `retardation_factor` | numeric | dimensionless | Linear retardation factor $R$. |
| `decay_rate_s_1` | numeric | s<sup>-1</sup> | First-order decay coefficient $\lambda$. |
| `source_concentration_mg_L` | numeric | mg L<sup>-1</sup> | Inlet concentration $C_0$ during the pulse. |
| `source_start_s` | numeric | s | Pulse start time $t_0$. |
| `source_duration_s` | numeric | s | Pulse duration $\tau$. |
| `source_end_s` | numeric | s | Derived pulse end, $t_0+\tau$. |
| `dispersivity_m` | numeric | m | Derived dispersivity $D/v$. |
| `peclet_number` | numeric | dimensionless | Domain Péclet number $vL/D$. |
| `damkohler_number` | numeric | dimensionless | Advective Damköhler number $\lambda RL/v$. |
| `advective_travel_time_s` | numeric | s | Retarded travel time $RL/v$. |

### `synthetic_adr1d_field.csv`

Each row is one analytical concentration at a scenario, time, and position.

| Column | Type | Unit | Description |
|---|---|---|---|
| `scenario_id` | string | - | Foreign key to the scenario table. |
| `split` | category | - | Scenario-level data partition. |
| `time_s` | numeric | s | Elapsed time. |
| `x_m` | numeric | m | Distance from the inlet. |
| `concentration_mg_L` | numeric | mg L<sup>-1</sup> | Noise-free analytical concentration $C(x,t)$. |
| `normalized_concentration` | numeric | dimensionless | $C(x,t)/C_0$ for the corresponding scenario. |

### `synthetic_adr1d_sensor_observations.csv`

Each row is one virtual-sensor observation.

| Column | Type | Unit | Description |
|---|---|---|---|
| `observation_id` | string | - | Stable identifier combining scenario, sensor, and time index. |
| `scenario_id` | string | - | Foreign key to the scenario table. |
| `split` | category | - | Scenario-level data partition. |
| `sensor_id` | category | - | Fixed virtual-sensor identifier, `S01`-`S06`. |
| `x_m` | numeric | m | Sensor position measured from the inlet. |
| `time_s` | numeric | s | Synthetic sampling time. |
| `concentration_true_mg_L` | numeric | mg L<sup>-1</sup> | Noise-free analytical concentration. |
| `noise_std_mg_L` | numeric | mg L<sup>-1</sup> | Gaussian standard deviation used for the observation. |
| `concentration_observed_mg_L` | numeric | mg L<sup>-1</sup> | Nonnegative noisy value after applying the detection-limit rule. |
| `detection_limit_mg_L` | numeric | mg L<sup>-1</sup> | Synthetic reporting limit, fixed at 0.01. |
| `is_below_detection_limit` | boolean | - | Whether the value before reporting substitution was below the limit. |

## :twisted_rightwards_arrows: ADR1D Partitions and Leakage Prevention

Splitting was performed at the scenario level and stratified by transport
regime. All space-time points and sensor observations from a scenario belong to
the same partition. This prevents information from one physical realization
from appearing in both model fitting and evaluation.

| Split | Scenarios | Field rows | Sensor rows |
|---|---:|---:|---:|
| `train` | 210 | 524,790 | 61,740 |
| `validation` | 45 | 112,455 | 13,230 |
| `test` | 45 | 112,455 | 13,230 |
| **Total** | **300** | **749,700** | **88,200** |

Use the supplied partitions for comparable benchmark results. Any alternative
cross-validation scheme should group by `scenario_id`, never by individual
rows.

## :rocket: ADR1D Quick Start

Clone the repository and enter its root directory:

```bash
git clone https://github.com/gstinoco/ADR1D.git
cd ADR1D
```

The CSV files can be read without specialized software. The following example
uses pandas:

```python
import pandas as pd

root = "data_processed"

scenarios = pd.read_csv(f"{root}/synthetic_adr1d_scenarios.csv")
field = pd.read_csv(f"{root}/synthetic_adr1d_field.csv")
sensors = pd.read_csv(
    f"{root}/synthetic_adr1d_sensor_observations.csv",
    converters={
        "is_below_detection_limit": lambda value: value.lower() == "true"
    },
)

# Join exact fields to their physical parameters.
field_with_parameters = field.merge(
    scenarios,
    on=["scenario_id", "split"],
    how="left",
    validate="many_to_one",
)

# Preserve the scenario-level split.
train = field_with_parameters[field_with_parameters["split"] == "train"]
validation = field_with_parameters[
    field_with_parameters["split"] == "validation"
]
test = field_with_parameters[field_with_parameters["split"] == "test"]
```

### Recommended analytical practice

- Fit scalers, transformations, and feature-selection procedures on the
  training split only.
- Use `scenario_id`, `time_s`, and `x_m` as explicit keys; do not rely on row
  order when reshaping fields.
- Treat the 300 scenarios as the independent physical realizations. The
  749,700 field rows are repeated space-time outputs, not 749,700 independent
  samples.
- Treat `concentration_true_mg_L` as a noise-free target and
  `concentration_observed_mg_L` as a reported synthetic measurement.
- Do not interpret the substituted value 0.005 mg L<sup>-1</sup> as an exact
  measurement. Retain `is_below_detection_limit` in analyses of censored data.
- Report performance by transport regime in addition to aggregate metrics.
- Account for the 83.23% below-limit proportion in arrival-detection or
  classification tasks.
- State clearly whether a study uses the exact field, noisy sensors, or both.

## :white_check_mark: Validation & Quality Control

Before this processed-data distribution was assembled, the canonical
generation workflow checked:

- file dimensions, column order, identifiers, and scenario uniqueness;
- scenario-level partition separation and regime constraints;
- derived parameters and dimensionless numbers;
- the initial condition and prescribed inlet pulse;
- 14,700 independent analytical recalculations from the field table;
- the differential-equation residual at 1,982 interior points using centered
  differences;
- all 88,200 noise-free sensor concentrations;
- the Gaussian noise model, nonnegativity rule, detection limit, and reporting
  substitution; and
- the dimensions and integrity of the distributed files.

The canonical validation completed with status `ok`. The maximum absolute
error among the independently recalculated analytical values was below
1.7&times;10<sup>-10</sup> mg L<sup>-1</sup>. The initial-condition and inlet-boundary
errors were zero at the stored output points. The maximum absolute PDE residual
was 4.79&times;10<sup>-7</sup> mg L<sup>-1</sup> s<sup>-1</sup>, and the 99th percentile of the
relative residual was 3.03&times;10<sup>-4</sup>.

## :lock: Release Identity

The files under `data_processed/` constitute the dataset snapshot distributed
with ADR1D version `1.0.0`. Their integrity was checked before publication.
Repository history and the release version identify this snapshot without
duplicating low-level integrity values in the public documentation.

Any modification to values, scenario assignments, serialized precision, source
records, or row ordering should be published under a new version.

## :dart: ADR1D Intended Uses

- Surrogate modeling of $C(x,t)$ from transport and source parameters.
- Inverse estimation of $v$, $D$, $R$, $\lambda$, $C_0$, $t_0$, or $\tau$.
- Full-field reconstruction from sparse virtual sensors.
- Plume-arrival and early-detection experiments.
- Comparison of numerical solvers with machine-learning or deep-learning
  models.
- Evaluation of models across conservative, reactive, and retarded regimes.

## :warning: ADR1D Limitations and Out-of-Scope Uses

- ADR1D is synthetic and is not calibrated to a particular aquifer, river,
  soil profile, contaminant, or monitoring network.
- The medium is one-dimensional, homogeneous, and stationary within each
  scenario.
- Spatial heterogeneity, transient flow, nonlinear reactions, multispecies
  chemistry, and coupled flow are not represented.
- The sampled interval ends at 1,000 m, but the analytical model is
  semi-infinite; the dataset must not be interpreted as imposing an outlet
  boundary at the last sensor.
- Parameter ranges were selected for methodological coverage rather than as a
  probability model for a real site.
- Parameters were sampled independently within the stated design, except for
  regime constraints and derived quantities.
- The effective number of independent physical realizations is 300; pointwise
  rows within a scenario are strongly related through the analytical model.
- Sensor errors are independent and Gaussian, without drift, temporal
  correlation, calibration bias, or position uncertainty.
- A single idealized detection limit and half-limit substitution rule are used.
- The large proportion of below-limit observations can dominate unstratified
  error metrics.
- The training, validation, and test scenarios share the same parameter ranges.
  They support interpolation tests within the design space, not claims of
  extrapolation or out-of-distribution generalization.
- Analytical labels contain no numerical-solver error; performance on ADR1D
  does not by itself demonstrate transfer to discretized or field data.

The dataset is suitable for methodological benchmarking. It should not be used
for site-specific environmental decisions without independent field data,
calibration, and a model appropriate to the site.

## :ocean: WQP Observational Component

### Source and retrieval

WQP-NM-Nutrients is a processed snapshot of records made publicly accessible
through the [Water Quality Portal](https://www.waterqualitydata.us/wqp_description/),
a cooperative service of the National Water Quality Monitoring Council, USGS,
and EPA. The extract covers stream locations in New Mexico, the WQP
`Nutrient` characteristic type, and a result-query window from January 1, 2022,
through July 14, 2026.

The canonical files were retrieved on July 14, 2026, with these requests:

- [Result query](https://www.waterqualitydata.us/data/Result/search?statecode=US%3A35&siteType=Stream&characteristicType=Nutrient&startDateLo=01-01-2022&startDateHi=07-14-2026&mimeType=csv&sorted=no)
- [Station query](https://www.waterqualitydata.us/data/Station/search?statecode=US%3A35&siteType=Stream&characteristicType=Nutrient&mimeType=csv&zip=no)
- [Monitoring-location summary query](https://www.waterqualitydata.us/data/summary/monitoringLocation/search?statecode=US%3A35&siteType=Stream&characteristicType=Nutrient&mimeType=csv&zip=no&dataProfile=periodOfRecord&summaryYears=5)

WQP is a live service. Repeating these requests can return a different snapshot
as providers revise or add records. The tables included with ADR1D version
`1.0.0` constitute the processed snapshot distributed here.

### Curation method

The source result and station files are preserved in the internal archive. The
public tables were produced without imputing concentrations or converting
units:

1. Select and rename fields needed for provenance, sampling context,
   qualification, analytical method, and source status.
2. Generate a stable local `observation_id` while retaining WQP activity,
   organization, provider, and monitoring-location identifiers.
3. Parse `ResultMeasureValue` into `result_value` when numeric and preserve the
   original text in `raw_result_value`.
4. Flag records with detection or quantitation conditions instead of assigning
   replacement concentrations.
5. Create the `model_ready` subset only from numeric records with a reported
   unit and no detection or quantitation condition.
6. Retain one station record for each monitoring location used by the
   observations.

The name `model_ready` means that the first structural filter has been applied.
It does **not** mean that analytes, units, chemical bases, sampling fractions,
methods, or source statuses have been harmonized for a particular model.

### Coverage and quality summary

| Item | Value |
|---|---:|
| Processed observations | 9,932 |
| Numeric source values | 5,456 |
| First-stage numeric subset | 5,360 |
| Monitoring locations used | 342 |
| Locations missing coordinates | 0 |
| Contributing organizations | 15 |
| Earliest / latest sample | 2022-01-05 / 2026-05-20 |

Provider coverage is not equally current:

| Provider | Rows | Earliest sample | Latest sample |
|---|---:|---:|---:|
| `NWIS` | 2,290 | 2022-02-01 | 2023-07-20 |
| `STORET` | 7,642 | 2022-01-05 | 2026-05-20 |

The legacy WQP interface used for the canonical download does not include
recent USGS records. The observed NWIS maximum above is therefore a property
of this snapshot, not evidence that USGS sampling stopped in 2023.

| Source result status | Rows |
|---|---:|
| `Final` | 7,510 |
| `Preliminary` | 1,467 |
| `Accepted` | 955 |

| Detection or quantitation condition | Rows |
|---|---:|
| None reported | 5,471 |
| `Not Detected` | 2,477 |
| `Present Below Quantification Limit` | 1,945 |
| `Detected Not Quantified` | 39 |

The most frequent reported characteristics are:

| Characteristic | Rows |
|---|---:|
| Phosphorus | 1,636 |
| Nitrate | 1,074 |
| Nitrite | 1,018 |
| Nitrate + Nitrite | 1,008 |
| Ammonia-nitrogen | 876 |
| Total Kjeldahl nitrogen (Organic N & NH3) | 737 |
| Kjeldahl nitrogen | 724 |
| Orthophosphate | 410 |
| Ammonia | 369 |
| Total Phosphorus, mixed forms | 315 |
| Ammonia and ammonium | 312 |
| Nitrogen | 306 |
| Total Nitrogen, mixed forms | 268 |
| Nitrogen, mixed forms (NH3), (NH4), organic, (NO2) and (NO3) | 267 |
| Organic Nitrogen | 214 |

### Contributing organizations

The organization fields are part of the data provenance and should be retained
in redistributed or derived tables.

| Organization ID | Organization | Rows |
|---|---|---:|
| `21NMEX_WQX` | NM Environmental Dept./SWQB | 2,932 |
| `USGS-NM` | USGS New Mexico Water Science Center | 2,290 |
| `PUEBLOISLETA` | Pueblo of Isleta, New Mexico (Tribal) | 1,429 |
| `POLSWATER_WQX` | Pueblo of Laguna (Tribal) | 838 |
| `SANDIAWQ_WQX` | Pueblo of Sandia Water Quality Program (New Mexico) | 693 |
| `TAOSPBLO_WQX` | Pueblo of Taos (Tribal) | 430 |
| `SANTACLARAPBLO` | Pueblo of Santa Clara | 407 |
| `PUEBLOJEMEZ` | Pueblo of Jemez (Tribal) | 216 |
| `PUEBLO_POJOAQUE` | Pueblo of Pojoaque (Tribal) | 170 |
| `DRMPWQX` | Mescalero Apache Tribe DRMP (Tribal) | 168 |
| `11NPSWRD_WQX` | National Park Service Water Resources Division | 159 |
| `ZIAPUEBLO_WQX` | Zia Pueblo | 103 |
| `SANFELIPE_WQX` | San Felipe Pueblo (Tribal) | 72 |
| `TCEQMAIN` | Texas Commission on Environmental Quality | 19 |
| `PUEBLO_SANTAANA` | Pueblo of Santa Ana, New Mexico | 6 |

### WQP observation fields

The `observations` and `model_ready` files have the same 31 columns.

| Field | Type / unit | Description |
|---|---|---|
| `observation_id` | string | Stable identifier generated for this release. |
| `organization_id` | string | Identifier of the organization that owns or supplied the source record. |
| `organization_name` | string | Formal name of the source organization. |
| `provider` | category | WQP source system: `NWIS` or `STORET`. |
| `activity_id` | string | Source sampling-activity identifier. |
| `activity_type` | string | WQP activity-type code. |
| `sample_date` | ISO date | Sampling-activity start date. |
| `sample_time` | local time | Reported activity start time, when available. |
| `time_zone` | string | Time-zone code associated with `sample_time`. |
| `monitoring_location_id` | string | Key used to join observations to stations. |
| `sample_media` | string | Environmental medium sampled. |
| `sample_media_subdivision` | string | Reported subdivision of the sample medium. |
| `hydrologic_condition` | string | Hydrologic condition reported for the activity. |
| `hydrologic_event` | string | Hydrologic event reported for the activity. |
| `characteristic_name` | string | Nutrient or nutrient-related characteristic. |
| `sample_fraction` | string | Fraction or filtering status reported for the result. |
| `result_value` | numeric; see `result_unit` | Parsed result; blank for censored, missing, or nonnumeric source values. |
| `result_unit` | string | Unit and chemical basis exactly as reported. |
| `is_numeric_result` | boolean | Whether the source value was parsed as numeric. |
| `is_censored_or_qualified` | boolean | Whether WQP reported a detection or quantitation condition. |
| `detection_condition` | string | Detection or quantitation condition. |
| `measure_qualifier` | string | Qualifier code attached to the measure. |
| `result_status` | category | Source status: `Accepted`, `Final`, or `Preliminary`. |
| `result_value_type` | string | WQP classification of the result value. |
| `usgs_parameter_code` | string | USGS parameter code when supplied by NWIS. |
| `analytical_method_id` | string | Identifier of the analytical method. |
| `analytical_method_context` | string | Vocabulary or organization defining the method identifier. |
| `analytical_method_name` | string | Reported analytical-method name. |
| `laboratory_name` | string | Reported laboratory name. |
| `raw_result_value` | string | Original, unparsed `ResultMeasureValue` text. |
| `source_file` | string | Preserved source filename from which the row was derived. |

Blank cells represent information not supplied in the selected WQP profile;
the files do not use a separate missing-value token.

### WQP station fields

| Field | Type / unit | Description |
|---|---|---|
| `monitoring_location_id` | string | Primary key matching the observation tables. |
| `organization_id` | string | Identifier of the source organization. |
| `organization_name` | string | Formal name of the source organization. |
| `provider` | category | WQP source system: `NWIS` or `STORET`. |
| `monitoring_location_name` | string | Name assigned by the source organization. |
| `monitoring_location_type` | string | WQP monitoring-location type. |
| `huc8` | string | Eight-digit hydrologic unit code. |
| `latitude` | decimal degrees | Monitoring-location latitude. |
| `longitude` | decimal degrees | Monitoring-location longitude. |
| `horizontal_datum` | string | Horizontal coordinate reference datum. |
| `country_code` | string | Reported country code. |
| `state_code` | string | Reported state code. |
| `county_code` | string | Reported county code. |
| `drainage_area_value` | numeric | Reported drainage area, when available. |
| `drainage_area_unit` | string | Unit for `drainage_area_value`. |
| `source_file` | string | Preserved source filename from which the row was derived. |

### WQP quick start

```python
import pandas as pd

root = "data_processed"

observations = pd.read_csv(
    f"{root}/wqp_nm_stream_nutrients_2022_2026_observations.csv"
)
numeric_subset = pd.read_csv(
    f"{root}/wqp_nm_stream_nutrients_2022_2026_model_ready.csv"
)
stations = pd.read_csv(
    f"{root}/wqp_nm_stream_nutrients_2022_2026_stations.csv",
    dtype={"huc8": "string", "state_code": "string", "county_code": "string"},
)

observations_with_locations = observations.merge(
    stations,
    on="monitoring_location_id",
    how="left",
    validate="many_to_one",
    suffixes=("_observation", "_station"),
)

# Example conservative analysis subset; chemistry-aware unit harmonization is
# still required before comparing concentrations across characteristics.
final_numeric = numeric_subset[numeric_subset["result_status"] == "Final"]
```

### WQP rights and attribution

EPA describes WQP as a public download and analysis resource, while the WQX
metadata identify contributing organizations as the primary owners of their
records. This release therefore follows a scoped-rights approach:

- The authors claim responsibility for query design, selection, field mapping,
  filtering, documentation, and validation of the processed snapshot.
- No ownership of the original WQP observations is claimed.
- No license assigned to ADR1D is extended to the WQP-derived tables.
- `organization_id`, `organization_name`, and `provider` must remain available
  so individual source records retain their attribution.
- Users should cite WQP, state the access date and query scope, and consult the
  source metadata before reuse in consequential analyses.

The [EPA citation guidance](https://www.epa.gov/waterdata/frequent-questions-water-quality-exchange-wqx)
and the USGS `dataRetrieval` citation record support the following source
citation:

> National Water Quality Monitoring Council (2026). *Water Quality Portal*.
> https://doi.org/10.5066/P9QRKUVJ. Accessed July 14, 2026. New Mexico;
> site type: Stream; characteristic type: Nutrient; result-query window:
> January 1, 2022-July 14, 2026.

### WQP limitations

- These are discrete observational water-quality records, not a
  PDE-complete transport benchmark.
- Velocity, discharge, dispersion, porosity, initial conditions, and boundary
  conditions are generally unavailable in the result records.
- Units and chemical bases are preserved as reported. For example, `mg/L`,
  `mg/l as N`, and `mg/l as P` are not interchangeable without a
  chemistry-aware conversion.
- Nondetects and other qualified results require censored-data methods; the
  blank numeric cells in `observations` are not zeros.
- The `model_ready` subset excludes qualified results and can introduce
  selection bias if used without the complete observation table.
- Preliminary records are included and may be revised by their providers.
- NWIS and STORET have different temporal coverage in this snapshot.
- Station coordinates and measurements are reproduced from source records and
  have not been independently field-verified by the curators.
- WQP is dynamic; later retrievals may not reproduce the same rows.

## :memo: How to Cite

### ADR1D

Machine-readable citation metadata are provided in [`CITATION.cff`](CITATION.cff).
The formal dataset citation includes the three principal researchers; student
contributors are recognized in the research-team section below.

Please cite the repository as:

> Tinoco-Guerrero, G., Domínguez-Mota, F. J., & Guzmán-Torres, J. A. (2026).
> *ADR1D and WQP-NM-Nutrients: A reproducible contaminant-transport benchmark
> and curated water-quality snapshot*
> (Version 1.0.0) [Data set]. Universidad Michoacana de San Nicolás de Hidalgo.
> https://doi.org/10.5281/zenodo.21499528

BibTeX:

```bibtex
@misc{TinocoGuerrero2026ADR1D,
  author    = {Tinoco-Guerrero, Gerardo and
               Domínguez-Mota, Francisco J. and
               Guzmán-Torres, J. Alberto},
  title     = {{ADR1D} and {WQP-NM-Nutrients}: A Reproducible
               Contaminant-Transport Benchmark and Curated
               Water-Quality Snapshot},
  year      = {2026},
  publisher = {Universidad Michoacana de San Nicolás de Hidalgo},
  note      = {Data set, version 1.0.0},
  doi       = {10.5281/zenodo.21499528},
  url       = {https://doi.org/10.5281/zenodo.21499528}
}
```

Cite the methodological sources below when the analytical model or sampling
design is material to the study.

### WQP-NM-Nutrients

When using the curated WQP tables, cite both the processed release and the
original portal:

> Tinoco-Guerrero, G., Domínguez-Mota, F. J., Guzmán-Torres, J. A. (2026).
> *WQP-NM-Nutrients: Curated New Mexico stream-nutrient observations,
> 2022-2026 query window* [Data set]. Universidad Michoacana de San Nicolás de
> Hidalgo. https://github.com/gstinoco/ADR1D. Source data: National Water
> Quality Monitoring Council, *Water Quality Portal*,
> https://doi.org/10.5066/P9QRKUVJ, accessed July 14, 2026.

Publications should also state the actual WQP filters and retain the
source-organization attribution in derived archives.

## :books: Scientific References

1. Ogata, A., and Banks, R. B. (1961). *A solution of the differential
   equation of longitudinal dispersion in porous media*. U.S. Geological
   Survey Professional Paper 411-A, pp. A1-A7.
   [https://doi.org/10.3133/pp411A](https://doi.org/10.3133/pp411A)
2. Chen, J.-S., and Liu, C.-W. (2011). Generalized analytical solution for
   advection-dispersion equation in finite spatial domain with arbitrary
   time-dependent inlet boundary condition. *Hydrology and Earth System
   Sciences*, 15, 2471-2479.
   [https://doi.org/10.5194/hess-15-2471-2011](https://doi.org/10.5194/hess-15-2471-2011)
3. McKay, M. D., Beckman, R. J., and Conover, W. J. (1979). Comparison of three
   methods for selecting values of input variables in the analysis of output
   from a computer code. *Technometrics*, 21(2), 239-245.
   [https://doi.org/10.1080/00401706.1979.10489755](https://doi.org/10.1080/00401706.1979.10489755)

---

## :scientist: Research Team

<div align="center">

### :star2: Meet the Team

*Researchers and students advancing traceable environmental data and reproducible transport benchmarks*

</div>

### :busts_in_silhouette: Main Researchers

<table align="center">
  <thead>
    <tr>
      <th align="center" width="120">Photo</th>
      <th align="left">Researcher</th>
      <th align="left">Affiliation</th>
      <th align="left">Contact</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/gtinoco.webp" alt="Gerardo Tinoco-Guerrero" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Gerardo Tinoco-Guerrero</b><br/><sub>Numerical methods and environmental modeling</sub></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td>
        <a href="mailto:gerardo.tinoco@umich.mx"><img alt="Email Gerardo Tinoco-Guerrero" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a><br/>
        <a href="https://orcid.org/0000-0003-3119-770X"><img alt="ORCID 0000-0003-3119-770X" src="https://img.shields.io/badge/ORCID-0000--0003--3119--770X-A6CE39?logo=orcid"></a>
      </td>
    </tr>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/dmota.webp" alt="Francisco J. Domínguez-Mota" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Francisco J. Domínguez-Mota</b><br/><sub>Applied mathematics and numerical methods</sub></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:francisco.mota@umich.mx"><img alt="Email Francisco J. Domínguez-Mota" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a><br/><a href="https://orcid.org/0000-0001-6837-172X"><img alt="ORCID 0000-0001-6837-172X" src="https://img.shields.io/badge/ORCID-0000--0001--6837--172X-A6CE39?logo=orcid"></a></td>
    </tr>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/jagt.webp" alt="J. Alberto Guzmán-Torres" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>J. Alberto Guzmán-Torres</b><br/><sub>Engineering applications and artificial intelligence</sub></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:jose.alberto.guzman@umich.mx"><img alt="Email J. Alberto Guzmán-Torres" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a><br/><a href="https://orcid.org/0000-0002-9309-9390"><img alt="ORCID 0000-0002-9309-9390" src="https://img.shields.io/badge/ORCID-0000--0002--9309--9390-A6CE39?logo=orcid"></a></td>
    </tr>
  </tbody>
</table>

### :mortar_board: Ph.D. Research Students

<table align="center">
  <thead>
    <tr>
      <th align="center" width="120">Photo</th>
      <th align="left">Student</th>
      <th align="left">Institution</th>
      <th align="left">Contact</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/gpj.webp" alt="Gabriela Pedraza-Jiménez" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Gabriela Pedraza-Jiménez</b><br/><img alt="Ph.D. research student" src="https://img.shields.io/badge/Ph.D.-Research%20Student-2E8B57?style=flat-square"></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:2220157h@umich.mx"><img alt="Email Gabriela Pedraza-Jiménez" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a></td>
    </tr>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/eci.webp" alt="Eli Chagolla-Inzunza" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Eli Chagolla-Inzunza</b><br/><img alt="Ph.D. research student" src="https://img.shields.io/badge/Ph.D.-Research%20Student-2E8B57?style=flat-square"></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:1137626b@umich.mx"><img alt="Email Eli Chagolla-Inzunza" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a></td>
    </tr>
  </tbody>
</table>

### :mortar_board: M.Sc. Research Students

<table align="center">
  <thead>
    <tr>
      <th align="center" width="120">Photo</th>
      <th align="left">Student</th>
      <th align="left">Institution</th>
      <th align="left">Contact</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/jlgf.webp" alt="Jorge L. González-Figueroa" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Jorge L. González-Figueroa</b><br/><img alt="M.Sc. research student" src="https://img.shields.io/badge/M.Sc.-Research%20Student-3B6EA8?style=flat-square"></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:1718717h@umich.mx"><img alt="Email Jorge L. González-Figueroa" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a></td>
    </tr>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/cnmb.webp" alt="Christopher N. Magaña-Barocio" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Christopher N. Magaña-Barocio</b><br/><img alt="M.Sc. research student" src="https://img.shields.io/badge/M.Sc.-Research%20Student-3B6EA8?style=flat-square"></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:1339846k@umich.mx"><img alt="Email Christopher N. Magaña-Barocio" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a></td>
    </tr>
  </tbody>
</table>

### :mortar_board: Undergraduate Research Students

<table align="center">
  <thead>
    <tr>
      <th align="center" width="120">Photo</th>
      <th align="left">Student</th>
      <th align="left">Institution</th>
      <th align="left">Contact</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" width="120">
        <img src="docs/team/mgfl.webp" alt="Maria Goretti Fraga-Lopez" width="96" height="96" style="border-radius: 50%;">
      </td>
      <td><b>Maria Goretti Fraga-Lopez</b><br/><img alt="Undergraduate research student" src="https://img.shields.io/badge/Undergraduate-Research%20Student-7B5B3A?style=flat-square"></td>
      <td><a href="https://umich.mx/"><img alt="University: UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B"></a></td>
      <td><a href="mailto:1702174b@umich.mx"><img alt="Email Maria Goretti Fraga-Lopez" src="https://img.shields.io/badge/Email-Contact-3B6EA8"></a></td>
    </tr>
  </tbody>
</table>

Student contributors are recognized for their participation in the broader
research program. Formal dataset citation and copyright attribution remain
limited to the three principal researchers listed in the citation section and
the license file.

---

## :factory: Industry Partners Supporting Innovation

<div align="center">

### :star2: Academic-Industry Collaboration

*Connecting reproducible environmental data with applied engineering and technology transfer*

</div>

<table align="center" width="70%">
  <tr>
    <td valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://www.siiia.com.mx/"><img src="docs/partners/siiia.webp" alt="SIIIA MATH institutional logo" width="240"></a><br/><br/>
        <b>SIIIA MATH</b><br/>
        <sub>Soluciones en Ingeniería</sub><br/><br/>
        <a href="https://www.siiia.com.mx/"><img alt="SIIIA MATH website" src="https://img.shields.io/badge/Website-SIIIA%20MATH-0B1B3A?style=for-the-badge"></a>
        <img alt="Partnership type" src="https://img.shields.io/badge/Type-R%26D%20and%20Engineering-457B9D?style=flat-square">
      </div>
      <br/>
      <b>Focus areas</b>
      <ul>
        <li>Mathematical modeling and scientific computing</li>
        <li>Environmental data products and reproducible benchmarks</li>
        <li>Applied research, development, and technology transfer</li>
      </ul>
    </td>
  </tr>
</table>

---

## :page_facing_up: License & Rights

License scope must be read by component:

- **ADR1D and original documentation:** the three author-generated ADR1D CSV
  files and the original documentation are licensed under
  [Creative Commons Attribution 4.0 International (`CC BY 4.0`)](LICENSE).
  Reuse is permitted with appropriate attribution, a link to the license, and
  an indication of changes.
- **WQP-NM-Nutrients:** the source observations were made publicly accessible
  through WQP and remain attributed to their contributing organizations. The
  curators do not apply the ADR1D license or assert ownership over those source
  records. Reusers should preserve provenance, cite WQP, and consult source
  metadata for the intended use.

The licenses of methodological publications do not determine the rights of
either dataset component.

Institutional emblems and logos under `docs/partners/` remain the property of
their respective organizations. They are used solely for identification and
acknowledgment and are not covered by the repository's `CC BY 4.0` license.

---

## :pray: Acknowledgments

<div align="center">

### :heart: Special Thanks

*We thank the institutions and partners whose continuing support sustains this research, its public data products, and student participation.*

</div>

### :classical_building: Institutional Support

<table align="center" width="100%" cellspacing="12">
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://umich.mx/"><img src="docs/partners/umsnh.webp" alt="UMSNH institutional emblem" width="180"></a><br/><br/>
        <b>Universidad Michoacana de San Nicolás de Hidalgo</b><br/>
        <sub>UMSNH · Academic institution · Mexico</sub><br/><br/>
        <a href="https://umich.mx/"><img alt="UMSNH website" src="https://img.shields.io/badge/Website-UMSNH-7A0019?style=flat-square"></a>
        <img alt="Institution type" src="https://img.shields.io/badge/Type-University-1A3A6B?style=flat-square">
        <img alt="Support type" src="https://img.shields.io/badge/Support-Infrastructure%20%26%20Funding-2E8B57?style=flat-square">
      </div>
      <br/>
      <b>Support provided</b>
      <ul>
        <li>Research infrastructure and institutional backing</li>
        <li>Academic supervision and undergraduate and graduate training</li>
      </ul>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://secihti.mx/"><img src="docs/partners/secihti.webp" alt="SECIHTI institutional logo" width="180"></a><br/><br/>
        <b>Secretaría de Ciencia, Humanidades, Tecnología e Innovación</b><br/>
        <sub>SECIHTI · Federal science agency · Mexico</sub><br/><br/>
        <a href="https://secihti.mx/"><img alt="SECIHTI website" src="https://img.shields.io/badge/Website-SECIHTI-2D6A4F?style=flat-square"></a>
        <img alt="Institution type" src="https://img.shields.io/badge/Type-Government-3A5A40?style=flat-square">
        <img alt="Support type" src="https://img.shields.io/badge/Support-Research%20Funding-40916C?style=flat-square">
      </div>
      <br/>
      <b>Support provided</b>
      <ul>
        <li>Financial support for scientific and technological research</li>
        <li>Promotion of knowledge generation and public dissemination</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://cimne.com/"><img src="docs/partners/cimne.webp" alt="CIMNE institutional logo" width="180"></a><br/><br/>
        <b>International Centre for Numerical Methods in Engineering</b><br/>
        <sub>CIMNE · Research center and international collaboration</sub><br/><br/>
        <a href="https://cimne.com/"><img alt="CIMNE website" src="https://img.shields.io/badge/Website-CIMNE-EE9B00?style=flat-square"></a>
        <img alt="Institution type" src="https://img.shields.io/badge/Type-Research%20Center-BB3E03?style=flat-square">
        <img alt="Support type" src="https://img.shields.io/badge/Support-Collaboration%20%26%20Training-CA6702?style=flat-square">
      </div>
      <br/>
      <b>Support provided</b>
      <ul>
        <li>Collaboration in numerical methods and computational engineering</li>
        <li>Research exchange, training, and international scientific links</li>
      </ul>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://www.siiia.com.mx/"><img src="docs/partners/siiia.webp" alt="SIIIA MATH institutional logo" width="180"></a><br/><br/>
        <b>SIIIA MATH: Soluciones en Ingeniería</b><br/>
        <sub>Engineering and innovation partner</sub><br/><br/>
        <a href="https://www.siiia.com.mx/"><img alt="SIIIA MATH website" src="https://img.shields.io/badge/Website-SIIIA%20MATH-0B1B3A?style=flat-square"></a>
        <img alt="Institution type" src="https://img.shields.io/badge/Type-Industry%20Partner-1D3557?style=flat-square">
        <img alt="Support type" src="https://img.shields.io/badge/Support-Funding%20%26%20Transfer-457B9D?style=flat-square">
      </div>
      <br/>
      <b>Support provided</b>
      <ul>
        <li>Applied research and engineering development</li>
        <li>Financial support and technology-transfer perspective</li>
      </ul>
    </td>
  </tr>
</table>

### :building_with_garden: Research Centers & Collaborations

<table align="center" width="100%" cellspacing="12">
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://aulas.cimne.com/aula/aula-morelia/"><img src="docs/partners/cimne.webp" alt="CIMNE institutional logo" width="180"></a><br/><br/>
        <b>Aula CIMNE Morelia</b><br/>
        <sub>Research collaboration and training space</sub><br/><br/>
        <a href="https://aulas.cimne.com/aula/aula-morelia/"><img alt="Aula CIMNE Morelia website" src="https://img.shields.io/badge/Website-Aula%20CIMNE%20Morelia-CA6702?style=flat-square"></a>
        <img alt="Research area" src="https://img.shields.io/badge/Area-Numerical%20Methods-EE9B00?style=flat-square">
      </div>
      <br/>
      <b>Collaboration highlights</b>
      <ul>
        <li>Numerical methods and computational engineering environment</li>
        <li>Research exchange and reproducible-computing training</li>
      </ul>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <a href="https://umich.mx/"><img src="docs/partners/umsnh.webp" alt="UMSNH institutional emblem" width="180"></a><br/><br/>
        <b>Coordinación de la Investigación Científica</b><br/>
        <sub>CIC-UMSNH · Institutional research coordination</sub><br/><br/>
        <a href="https://umich.mx/"><img alt="UMSNH website" src="https://img.shields.io/badge/Institution-UMSNH-7A0019?style=flat-square"></a>
        <img alt="Support area" src="https://img.shields.io/badge/Support-Research%20Development-2E8B57?style=flat-square">
      </div>
      <br/>
      <b>Collaboration highlights</b>
      <ul>
        <li>Institutional coordination for scientific research</li>
        <li>Support for data curation, documentation, and public dissemination</li>
      </ul>
    </td>
  </tr>
</table>

### :droplet: Environmental Data Providers

<table align="center" width="100%">
  <tr>
    <td valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <b>National Water Quality Monitoring Council and WQP contributing organizations</b><br/>
        <sub>Public environmental observations with record-level provenance</sub><br/><br/>
        <a href="https://www.waterqualitydata.us/"><img alt="Water Quality Portal" src="https://img.shields.io/badge/Data-Water%20Quality%20Portal-3B6EA8?style=flat-square"></a>
        <img alt="Provider count" src="https://img.shields.io/badge/Contributors-15%20Organizations-1F6F8B?style=flat-square">
        <img alt="Provenance" src="https://img.shields.io/badge/Provenance-Record%20Level-2E8B57?style=flat-square">
      </div>
      <br/>
      The authors acknowledge the organizations that make their monitoring
      records publicly accessible through WQP. Organization names and
      identifiers are retained in the distributed tables so provenance remains
      visible at record level.
    </td>
  </tr>
</table>

### :computer: Technology Communities

<div align="center">

| :package: Framework | :busts_in_silhouette: Community | :star: Contribution |
|:---:|:---:|:---:|
| [![Python](https://img.shields.io/badge/Python-Data%20Workflows-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/) | **Python Community** | Reproducible data-access and analysis examples |
| [![pandas](https://img.shields.io/badge/pandas-Tabular%20Data-150458?style=flat-square&logo=pandas)](https://pandas.pydata.org/) | **pandas Community** | CSV inspection, filtering, and analysis |

</div>

---

## :email: Contact & Support

<div align="center">

*Scientific questions, data corrections, and reproducibility support*

[![Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/gstinoco/ADR1D) [![Issues](https://img.shields.io/badge/GitHub-Open%20Issue-181717?style=flat-square&logo=github)](https://github.com/gstinoco/ADR1D/issues) [![Email](https://img.shields.io/badge/Email-Research%20Contact-3B6EA8?style=flat-square)](mailto:gerardo.tinoco@umich.mx)

</div>

<table align="center" width="100%" cellspacing="12">
  <tr>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <b>Primary Research Contact</b><br/>
        <sub>Scientific coordination and data provenance</sub>
      </div>
      <br/>
      <b>Gerardo Tinoco-Guerrero</b><br/>
      <sub>Universidad Michoacana de San Nicolás de Hidalgo<br/>Morelia, Michoacán, Mexico</sub>
      <br/><br/>
      <div align="center">
        <a href="mailto:gerardo.tinoco@umich.mx"><img alt="Email Gerardo Tinoco-Guerrero" src="https://img.shields.io/badge/Email-Contact-3B6EA8?style=flat-square"></a>
        <a href="https://orcid.org/0000-0003-3119-770X"><img alt="ORCID 0000-0003-3119-770X" src="https://img.shields.io/badge/ORCID-0000--0003--3119--770X-A6CE39?style=flat-square&logo=orcid"></a>
        <a href="https://umich.mx/"><img alt="UMSNH" src="https://img.shields.io/badge/University-UMSNH-1A3A6B?style=flat-square"></a>
      </div>
    </td>
    <td width="50%" valign="top" style="border: 1px solid #d0d7de; border-radius: 8px; padding: 16px;">
      <div align="center">
        <b>Repository Support</b><br/>
        <sub>Questions, corrections, and reproducibility reports</sub>
      </div>
      <br/>
      <ul>
        <li>Use GitHub Issues for reproducible data or documentation problems.</li>
        <li>Include the component, file name, row identifier, and expected result.</li>
        <li>Use email for scientific collaboration or provenance questions.</li>
      </ul>
      <div align="center">
        <a href="https://github.com/gstinoco/ADR1D/issues"><img alt="Open a GitHub issue" src="https://img.shields.io/badge/Open-GitHub%20Issue-181717?style=for-the-badge&logo=github"></a>
      </div>
    </td>
  </tr>
</table>

---

## :speech_balloon: FAQ

<details>
  <summary><b>Where are the distributed datasets located?</b></summary>
  <br/>
  All six CSV files are stored under <code>data_processed/</code>. The three
  <code>synthetic_adr1d_*.csv</code> files form the analytical benchmark, while
  the three <code>wqp_nm_stream_nutrients_*.csv</code> files form the separate
  observational component.
</details>

<details>
  <summary><b>Can ADR1D and WQP-NM-Nutrients be merged into one training table?</b></summary>
  <br/>
  No, not as observations from a common population. ADR1D is a controlled
  synthetic transport benchmark, whereas WQP-NM-Nutrients contains field
  observations from multiple organizations, locations, methods, units, and
  dates. They support complementary experiments but require separate scientific
  interpretations.
</details>

<details>
  <summary><b>Is the WQP <code>model_ready</code> table ready for every statistical or ML task?</b></summary>
  <br/>
  No. It is a conservative first-stage subset that removes nonnumeric,
  unit-missing, and censored results. Users must still harmonize chemical bases,
  units, characteristics, spatial support, temporal support, and study-specific
  quality criteria.
</details>

<details>
  <summary><b>May the WQP-derived tables be redistributed?</b></summary>
  <br/>
  The source records were made publicly accessible through WQP and are retained
  with provider and organization attribution. Cite WQP, preserve provenance,
  and review source metadata for consequential reuse. The repository's
  <code>CC BY 4.0</code> license applies only to the author-generated ADR1D
  component and original documentation.
</details>

<details>
  <summary><b>Can a later WQP query reproduce this snapshot exactly?</b></summary>
  <br/>
  Not necessarily. WQP is dynamic and providers may add or revise records. Use
  the versioned tables when exact snapshot identity matters; use the documented
  filters and access date when conducting an updated query.
</details>

---

<div align="center">

*Open transport benchmarks and traceable environmental data for reproducible research*

[![GitHub stars](https://img.shields.io/github/stars/gstinoco/ADR1D?style=social)](https://github.com/gstinoco/ADR1D/stargazers) [![GitHub forks](https://img.shields.io/github/forks/gstinoco/ADR1D?style=social)](https://github.com/gstinoco/ADR1D/forks) [![GitHub watchers](https://img.shields.io/github/watchers/gstinoco/ADR1D?style=social)](https://github.com/gstinoco/ADR1D/watchers)

<br/>

[![Repository](https://img.shields.io/badge/View-Repository-181717?style=flat-square&logo=github)](https://github.com/gstinoco/ADR1D) [![Citation](https://img.shields.io/badge/How%20to-Cite-7B5B3A?style=flat-square)](#memo-how-to-cite) [![License](https://img.shields.io/badge/License-CC%20BY%204.0-D4AF37?style=flat-square)](LICENSE)

<br/>

<b>If this dataset supports your research, please cite it and consider giving the repository a star.</b>

</div>
