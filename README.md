# BACP and MBACP-Q Instances

This repository contains benchmark instances related to the Balanced Academic Curriculum Problem (BACP) and multi-curriculum variants.

The instances describe academic planning data such as periods, courses, credits, and prerequisite relationships. They can be used to test curriculum balancing models and scheduling formulations.

## Contents

The repository includes:

- Base BACP instances such as `bacp8`, `bacp10`, and `bacp12`.
- Variant files such as `bacp8_1`, `bacp10_2`, and `bacp12_2`.
- Combined or multi-curriculum instances such as `mbacp12.txt`, `mbacp123.txt`, and `mbacp_4_01(8_1x10_2x11_1x12_2).txt`.

## File Structure

The plain-text files use section markers such as:

- `# P`: Number of periods.
- `# C`: Course data, including course identifier, credit/load information, and related parameters.
- `# R #`: Prerequisite relationships.

Some files use names that encode the source curricula used to build a combined instance.

## Suggested Use

These data files are suitable for optimization experiments in academic curriculum design, especially when comparing mathematical programming models or metaheuristics for balancing course loads under prerequisite constraints.
