# Contingency Simulation

This repository contains the data, code, and analysis relevant to *Self-Representation: Learning Contingency?*, a perceptual decision-making study. It was run in parallel to an ongoing theoretical integrative review, which assesses existing formal computational models of self-representation across the cognitive sciences. 

The review finds that self-representation, traditionally studied across 'levels' of self and interactive complexity (embodied, affective, agentic, social, narrative), can be understood as sharing a common computational goal : encoding the agent's position within the causal structure it perceives in its environment. This is hypothesised to develop primarily through patterns of contingency - causal relationships whose origin can be attributed to the self (kept intentionally distinct in name from Sense of Agency, SoA to avoid confusions between the terms).

The review proposes a layered inferential process: multisensory integration → causal inference → contingency. This experiment operationalises the contingency layer, by hypothesising that contingency is encoded through statistical learning : which properties co-occur reliably with self-indexed causality? When does the agent hold a distinct position in the causal network it observes? 
If this mechanism holds true, learnt property-indexed contingency would transfer across contexts, since it informs self-representation - broader priors over contingency and behavioural affordances over time. 

Property-indexed contingency is operationalised as `SC` in the following experiment - a condition in which action (press) reliably causes the reversal of dot motion. To test the validity of the hypothesis, the experiment was designed with OC (observed-causality) and R (random) conditions, offering alternative interpretations. Each subject performed 2 perceptual decision-making tasks, each sharing the SC property. 

Press rates, learning, and relationships between variables were assessed, alongside 4 candidate computational models. Details can be found below.

- **OSF Preregistration**: https://osf.io/uj92x
- **Data**: https://osf.io/eh4vq


## Experimental Design
- **Code setup for experimental design**: https://github.com/ninaedgley/property_contingency_exp

2 perceptual decision-making tasks for each subject (N = 70) - one involving dots moving in a circular fashion, the other involving squares crossing the screen from right to left. In both tasks, subjects were asked to determine when to press a spacebar, causing the shapes to either reverse their motion direction (T1), or to move upwards (T2). Their presses either caused the reversal, or did not : this depended on specific properties of the shapes.

**Block Structure**
1. 10 watch-only trials, in which subjects either observed random property-outcome relationships, or observed causal structure. This varied per group (described below).
2. 60 press-enabled trials, forming the bulk of observations and learning. For each trial, subjects had 4s to observe the motion of shapes and determine whether to press. 2s would pass (effort to avoid strong binding effects), before the outcome (reversal vs. no change) was revealed. 
3. 20 press-enabled trials, with no outcome shown.

Manipulations involved assigning properties to various roles, varying property assignments across tasks, and a between-subjects manipulation into two groups. Each is described below.

**Property Assignment**
- 3 visual properties were randomised : colour (red & blue in Task 1, green & purple in Task 2), size (large, small), and velocity (fast, slow).
- Properties were assigned one of 3 roles : SC (self-causal), OC (observed-causal), and R (random).
- For trials with SC active : dots would reverse (or squares would move upwards) if subjects pressed (p = 0.95), and would almost certainly not reverse if they did not press (p = 0.05). 
- For trials with OC active : dots would reverse (or squares would move upwards), regardless of whether the subjects pressed (p = 0.9).
- For trials with R active : dots would reverse (or squares would move upwards) minimally, regardless of what the subject did (p = 0.1).
- Within properties, specific values were assigned either active or inactive roles. For example : if `colour` was assigned the `SC` role, one of its values would be treated as active (red), and the other inactive (blue). Across the task, if the subject pressed on trials in which red dots appeared, the dots would reverse. Blue would not be predictive of contingency. As properties are present on all trials (size, colour, velocity being inherent to the visual representation in each task), values, rather than properties as a whole, needed to discriminate between contingency-affording circumstances and not.

**Task Manipulation**
- Task 1 property roles were assigned and kept constant throughout the trials.
- In Task 2, SC remains assigned to the same property - however, OC and R swap. If size was causally predictive of reversal, it became random in T2. Likewise, if velocity was predictive of random outcomes in T1, it became causally predictive of motion change in T2. 

**Group Manipulation**
- Subjects were randomly assigned (p = 0.5) to Group A, or Group B
- Group A's Block 1 trials (across both Task 1 and Task 2) had OC active : they were able to observe reversals and outcomes occurring at the same rate as the rest of the experiment. Since they were unable to press, this meant that they could observe the OC-assigned property reliably co-occurring with motion reversals.
- Group B's Block 1 trials (across both Task 1 and Task 2) showed random associations in reversals. No properties were active, and outcomes occurred randomly.
The rationale was to observe whether any priming effects could be discerned : if OC-observation in Group A reliably predicted higher SC or OC learning rates; on the other hand, whether observing random associations reduced the likelihood of learning causal relationships.


## Notebooks
1. `01_raw_data_analysis.ipynb` — Preprocessing
2. `02_EDA.ipynb` — Exploratory data analysis
3. `03_hypothesis_tests.ipynb` — Pre-registered hypothesis tests (H1–H4)
4. `04_model_specification.ipynb` — Model specifications
5. `05_psytrack_implementation.ipynb` — PsyTrack implementation 
6. `06_model_fitting.ipynb` — Model fitting [in progress]
7. `07_model_comparison.ipynb` — Model comparison and implications [in progress]


## Repo structure
data/ — cleaned and preprocessed data, derived parameters and weights
notebooks/ — code, analysis, and interpretations
output/ — plots and figures referenced from notebooks 01 - 04
psytrack_figures/ — plots referenced in notebook 05, specific to the PsyTrack implementation


## Setup
Notebooks should be run in order. Processed data are included under `data/processed/`; raw Prolific exports were excluded.
`python3.11 -m venv .venv`
`source .venv/bin/activate`
`python -m pip install -r requirements.txt`
`python -m ipykernel install --user --name contingency-simulation`


## Contact
E: nina.edgley@pm.me