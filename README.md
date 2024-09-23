# BugHunter: Bug-Aware Automated GUI Testing via Retrieval Augmentation

## Overview

BugHunter is a novel bug-aware automated GUI testing approach that leverages Large Language Models (LLMs) and Retrieval-Augmented Generation (RAG) to generate exploration paths guided by bug reports from similar apps. This method aims to increase bug detection efficiency by dynamically adapting the testing process to target bug paths, rather than focusing solely on coverage.

Here is the overview structure of BugHunter:

![](./assets/overview.png)

## Key Features
- Bug Knowledge Base: Constructs a high-quality bug knowledge base from historical bug reports.
- Two-Stage Retrieval: Retrieves relevant bug reports using a two-stage retrieval process.
- Path Generation: Generates test paths based on bug reports from similar apps.
- Local and Global Path Planning: Handles differences in functionality and UI design across apps.
- Efficient Bug Detection: Increases bug detection efficiency by targeting bug paths.

## Modules

1. Knowledge Base Construction
Extracts information from open-source apps and their bug reports.
Maps bug reports to the Activity Transition Graph (ATG) to form a structured knowledge base.
2. Similar Bug Retrieval
Uses a two-stage retrieval process to identify relevant bug reports.
Builds a test cognition graph to map similar app bug reports to the target app's ATG.
3. Bug-Augmented Path Generation
Annotates GUI screenshots to help LLMs interpret GUI elements accurately.
Uses local and global path planning to adapt bug-triggering steps to the target app's specific GUI layout.

## Implementation

BugHunter is implemented as a fully automated GUI testing tool, utilizing GPT-4 Vision for text and visual information processing, UIAutomator for GUI view hierarchy extraction, and BCEmbedding for similarity search and matching. The system is built on VirtualBox, Python pyvbox, and Android Debug Bridge (ADB).

## Experiments

### Research Questions
- RQ1: Evaluates BugHunter's effectiveness in detecting bugs and achieving test coverage compared to common and state-of-the-art baseline methods.
- RQ2: Ablation studies to evaluate the contribution of each sub-module to coverage and bug detection performance.
- RQ3: Assesses BugHunter's practicality by automatically exploring apps on Google Play and detecting unseen bugs.

### Datasets

- RQ1 & RQ2: 71 apps and 121 bugs from [Themis benchmark](https://github.com/the-themis-benchmarks/home) and [F-Droid](https://f-droid.org/).
- RQ3: 237 popular apps randomly selected from Google Play.

### Baseline Methods

Includes 16 common and state-of-the-art automated GUI testing techniques categorized into random/rule-based, model-based, and learning-based methods.

### Results

#### Bug Detection Performance (RQ1)

BugHunter detected 121 bugs in 71 apps with a recall rate of 64%, 20% higher than the best baseline method (GPTDroid).
Achieved 53% activity coverage and 52% code coverage, comparable to the best baseline.

#### Ablation Study (RQ2)

Removing the similar bug retrieval module and augmented path generation module reduced the bug detection recall rate by 50% and 51%, respectively.

#### Practicality (RQ3)

BugHunter detected 49 new crash bugs in 273 apps on Google Play, with 33 fixed, 9 confirmed by developers, and 7 pending feedback.
 

## Quick Start

Create your python env:

```
conda create -n bughunter python=3.10 -y
conda activate bughunter
```

Install the requirements packages:

```
pip install requirements.txt
```

To run the BugHunter, you should then:

1. Change your path in `src/config.ini`
2. Run `python main.py`

## Acknowledgments

For more details, please refer to the full paper.