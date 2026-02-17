# ResMerge Project Page

This is the project page for **ResMerge: Continual Adaptation of Pretrained Robot Policies via Residual RL and Model Merging**.

## Project Overview

ResMerge addresses the challenge of continually adapting pretrained generalist robot policies to new tasks. When a robot in a home or factory must sequentially learn 5–10 new tasks, existing methods suffer from:

- **Poor generalization** — IL-based PEFT methods fail to generalize to new task variants
- **Catastrophic forgetting** — Traditional fine-tuning causes the model to forget previously learned tasks

ResMerge proposes a new paradigm that combines:

- **Residual RL** — Learn each new task as a residual correction on top of a frozen base policy
- **Model merging** — Merge compatible residuals in parameter space to elicit and combine knowledge

## Key Contributions

- A new paradigm for continual adaptation of pretrained robot policies via residual RL and merging
- Exploration of model merging in residual RL with an improved merging metric for better success rates
- Strong generalization to new task variants while avoiding forgetting of old tasks

## Website Structure

The website contains:

- Project overview and highlights
- Problem formulation and challenges
- Method description with figures
- Experimental setup and task demonstrations
- Results and contributions
- Links to paper and code (coming soon)
