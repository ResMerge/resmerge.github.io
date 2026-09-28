# ResMerge Project Page

Anonymous project website for **ResMerge: Residual Policy Learning and Merging for Continual Adaptation of Pre-trained Robot Policies**.

Website: https://resmerge.github.io/

ResMerge learns residual corrections on top of a frozen base policy and uses Residual-Field Consistency (RFC) to merge compatible experts. Incompatible candidates remain separate, so the stored expert bank can grow.

## Experimental scope

- Simulation: LIBERO-Spatial and LIBERO-Object, with all ten tasks per suite for ViT-T and five selected tasks per suite for OpenVLA-OFT.
- Simulation residuals use state-based observations, including privileged object poses; real-robot residuals use frozen visual features and proprioception.
- Residual adaptation requires no additional expert demonstrations, but base-policy initialization uses demonstrations and adaptation requires online RL interaction.
- Reported post-merge success includes RL refinement on affected tasks.

## Results

The website reproduces Tables I–VII of the accompanying anonymous manuscript. FWT, AUC, and success rates are percentages; NBT is measured in percentage points. Table I reports mean ± standard deviation over five seeds.

On the real robot, ResMerge achieves FWT 50%, NBT 7 pp, and AUC 75%. Average final-stage success is 72.5% with two experts, compared with 78.75% with four experts without merging and 67.0% for TAIL. Average final-stage success and AUC are distinct metrics.

## Website contents

- Method overview and experimental setup
- Simulation, ablation, and real-robot result tables
- Sequential RFC diagnostics
- Representative successful and unsuccessful robot rollouts

The page retains anonymous authorship for double-anonymous review. It is based on the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template).
