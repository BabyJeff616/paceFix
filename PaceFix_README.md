# PaceFix

PaceFix is an iterative LLM-based Automated Program Repair (LLM-APR)
framework that improves multi-candidate repair through
functional-progress-guided state decision and cross-candidate structural
feedback.

## Overview

PaceFix extends the standard Generate-and-Validate repair process with
two mechanisms:

-   **State Decision**: selects the next repair state among candidates
    with maximum functional progress using program evidence.
-   **Progress-Conditioned Cross-Candidate Structural Feedback (PCSF)**:
    extracts structural signals from candidate patches and provides
    feedback for subsequent repair iterations.

## Environment

The experiments mainly require:

-   Python 3.x
-   Defects4J benchmark
-   Java development environment
-   LLM API access

Install the required dependencies before running experiments.

## Installation

Clone the repository:

``` bash
git clone https://github.com/BabyJeff616/paceFix.git
cd paceFix
```

Install dependencies:

``` bash
pip install -r requirements.txt
```

Configure API keys and experiment settings according to the provided
configuration files.

## Running Experiments

The experiment pipeline includes:

1.  LLM-based candidate patch generation.
2.  Patch compilation and test validation.
3.  State Decision and PCSF feedback generation.
4.  Iterative repair until termination.

Example:

``` bash
python main.py --config <config_file>
```

The exact command depends on the experiment configuration.

## Dataset

PaceFix is evaluated on Defects4J benchmarks, including:

-   Defects4J v1.2
-   Defects4J v2.0
-   Single-function bug repair scenarios

## Evaluation

The framework evaluates:

-   Plausible fixes
-   Correct fixes
-   Component ablation
-   Cross-LLM generalization

## License

This project is provided for research purposes.
