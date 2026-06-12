# Simplified Ripple Prototype

This repository contains a simplified Python prototype of Ripple, an intent-aware Change Impact Analysis (CIA) algorithm proposed in the paper:

"From Seed to Scope: Reasoning to Identify Change Impact Sets" (ICSE 2026)

## Purpose

The purpose of this implementation is to reproduce the main algorithmic workflow of Ripple in a simplified and self-contained manner for the Advanced Algorithms final assignment.

The original Ripple approach relies on Large Language Models (LLMs), repository mining, issue reports, and project-specific assets. Therefore, this implementation does not attempt to reproduce the original experimental results. Instead, it focuses on demonstrating the core algorithmic stages of Ripple.

## Implemented Workflow

The prototype implements the following stages:

1. Initial impact set construction from a seed edit location
2. Evolutionary coupling-based expansion using commit history
3. Dependence coupling-based expansion using call and class-member dependencies
4. Dependence clustering using connected components
5. Simplified change plan generation
6. Cluster-level impact prediction
7. Self-consistency-based refinement
8. Final impact set aggregation

## Implementation Design

The input consists of:

* Seed edit location
* Change intent
* Commit history
* Dependence graph
* Method summaries

The implementation first expands the candidate impact scope using historical co-change information and dependency relationships. The expanded methods are then grouped into dependence clusters.

Since the original Ripple system uses LLM-based Planner and Reasoner components, this prototype uses simplified heuristic approximations. The Planner generates a simplified change plan, while the Reasoner predicts impacted methods based on keyword overlap, dependency relationships, and historical co-change information.

To simulate Ripple's self-consistency strategy, multiple impact predictions are generated and combined through intersection before constructing the final impact set.

## How to Run

Open a terminal in the project directory and execute:

python ripple_prototype.py

## Example Execution Result

The program prints:

* Initial impact set
* Evolutionary coupling-based expansion
* Dependence coupling-based expansion
* Dependence clusters
* Simplified change plan
* Cluster-level predictions
* Final impact set
* Precision, Recall, and F1-score

Example result:

Precision: 0.83

Recall: 1.00

F1-score: 0.91

## Repository Structure

assignment_prototype/

├── ripple_prototype.py

└── README.md

## Limitations

This implementation is a simplified educational prototype.

The original Ripple system relies on LLM-based planning and reasoning, while this implementation uses heuristic approximations. In addition, the example dataset is manually constructed and does not originate from real-world repositories, issue trackers, or commit histories.

Therefore, the results produced by this prototype should not be interpreted as reproducing the original Ripple evaluation. The goal is to demonstrate the algorithmic workflow and interaction among the major components of Ripple.

## Author

Advanced Algorithms Final Assignment

Simplified Ripple Prototype Implementation
