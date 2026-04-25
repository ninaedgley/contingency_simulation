# Contingency Simulation — Analysis

Analysis code for property-indexed contingency learning experiment.

- **Experiment code**: https://github.com/ninaedgley/property_contingency_exp
- **Preregistration**: https://osf.io/uj92x
- **Data**: https://osf.io/eh4vq

## Notebooks

1. `01_raw_data_analysis.ipynb` — Data cleaning
2. `02_EDA.ipynb` — Exploratory data analysis
3. `03_hypothesis_tests.ipynb` — Pre-registered hypothesis tests (H1–H4)
4. `04_model_specification.ipynb` — Model specification
5. `05_model_fitting.ipynb` — Model fitting
6. `06_model_comparison.ipynb` — Model comparison and implications
7. `07_figures.ipynb`— Figures and data visualisations

# Property-indexed contingency learning

One paragraph: research question. Can contingency (self-causal efficacy) 
be acquired and generalised across visual contexts, or is it tracked as 
property-specific action-outcome associations that don't transfer.

## Theoretical framing
Two sentences linking to the integrative review (in /context). The review 
proposes a layered inferential process: multisensory integration → causal 
inference → contingency. This experiment operationalises the contingency layer.

## Experiment
Four sentences: N=70 Prolific subjects, 3 visual properties with randomised 
role assignment, 2 tasks with role swap for OC/R but SC constant, 3 blocks 
per task (watch-only, learning, no-feedback).

## Repo structure
notebooks/01_data_cleaning.ipynb — raw data ingestion and cleaning
notebooks/02_EDA.ipynb — exploratory analysis
notebooks/03_hypothesis_tests.ipynb — preregistered H1-H4
notebooks/04_model_specification.ipynb — computational model specifications
notebooks/05_psytrack_implementation.ipynb — PsyTrack weight trajectories
data/ — cleaned data, derived tables
figures/ — plots referenced in notebooks
context/ — theoretical review summary, prereg, experiment repo link

## Current status
Preregistered hypotheses tested (notebook 03). PsyTrack applied (notebook 05).
Computational models M1-M4 specified (notebook 04); fitting and comparison 
scheduled for notebook 06 (June 2026).

## Key findings so far
Three bullets, honest:
- H1: weak SC-R discrimination at group level.
- H2: SC transfer index consistent with zero.
- PsyTrack: OC weight trajectory shows partial learning and partial reset 
  across the task boundary; SC weight near zero throughout, consistent with 
  behavioural analyses.

## Preregistration
OSF link.

## Contact
Nina Edgley, [email].