# PaceFix

PaceFix is a multi-candidate iterative framework for LLM-based automated program repair. It combines functional-progress-constrained state decision with progress-conditioned cross-candidate structural feedback.

## Approach

PaceFix contains two complementary mechanisms:

- **State Decision** selects the candidate inherited as the next repair state. Compilation and test results first determine the maximum-progress candidate set. Failure-related dataflow evidence is used when multiple candidates achieve the same maximum functional progress.
- **Progress-Conditioned Cross-Candidate Structural Feedback (PCSF)** extracts repeated local structural signals from high-progress candidates and incorporates them into the next-round prompt.

## Dataset

The experiments use 483 single-function bugs from Defects4J:

| Dataset | Number of bugs |
|---|---:|
| Defects4J v1.2 | 255 |
| Defects4J v2.0 | 228 |

The evaluation assumes perfect function-level fault localization.

## Environment

The experimental environment includes:

- Linux
- Defects4J 2.0.0
- OpenJDK 8 for compilation and testing
- OpenJDK 21 for program analysis
- Joern 4.0.6
- GumTree with the Java JDT generator

Joern is used to analyze intra-procedural def-use relations. GumTree extracts AST edits between repair candidates and the current repair state.

## Repair Configuration

For each bug, PaceFix performs at most three repair rounds and generates up to 15 candidates per round. The total candidate-generation budget is 45, and the temperature is set to 1.

## Patch Evaluation

A patch that passes the complete original test suite is considered plausible. A plausible patch is considered correct if it is semantically equivalent to the intended repair represented by the developer patch.

The evaluation reports the numbers of plausibly and correctly fixed bugs. Each bug is counted at most once for each metric.

## Citation

If you use this implementation or its experimental results, please cite the accompanying PaceFix paper.
