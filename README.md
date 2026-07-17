# TrustSOC-Research

## Title

TrustSOC: Trust-Calibrated Multi-Evidence Cyber Reasoning Framework for SOC

## Overview

For the public GitHub upload, heavyweight local assets such as raw/processed data, trained model weights, predictions, figures, and full analysis dumps are intentionally excluded to keep the repository lightweight. They can be regenerated locally by rerunning the pipeline.

This repository implements a local, reproducible research prototype for TrustSOC — a framework that extends SOC automation by asking not only whether a model can classify a case correctly, but also **whether it knows when it should conclude, investigate, escalate, or refuse**.

The repository is designed for:

- local preprocessing with evidence extraction and DERG construction
- TrustSOC-DERG training and evaluation
- trust calibration with adaptive threshold learning
- DERG-style multi-evidence reasoning
- adversarial robustness benchmarking (7 attack types)
- explainability and evidence attribution
- temporal evidence analysis
- statistical significance testing with bootstrap CIs
 types


## Installation

```powershell
cd <project_directory>
python -m pip install -r requirements.txt
```

For the Transformer model, also install PyTorch:
```powershell
python -m pip install torch
```

## How to Run

```powershell
python main.py --mode preprocess
python main.py --mode train_baselines
python main.py --mode train_derg
python main.py --mode evaluate
python main.py --mode compare_opensoc
python main.py --mode robustness
python main.py --mode report
python main.py --mode xai
python main.py --mode deep_analysis
python main.py --mode practical_experiments
python main.py --mode full_analysis
```

Or use individual scripts:

```powershell
python scripts/run_preprocess.py
python scripts/train_derg.py
python scripts/evaluate.py
python scripts/compare_with_opensoc.py
python scripts/run_robustness.py
python scripts/generate_report_tables.py
python scripts/supporting_analysis/run_xai.py
python scripts/supporting_analysis/run_deep_analysis.py
python scripts/supporting_analysis/run_practical_experiments.py
python scripts/run_full_analysis.py
```

## Configuration

All paths are auto-detected relative to the project root. To override:


## Limitations

- TrustSOC-DERG requires PyTorch and may need GPU for efficient training.
- Expected action labels are heuristic targets derived from evidence rules, not human annotations.
- Temporal analysis uses heuristic half-life values; real CTI timestamps may vary.

## Future Work

- Enable a fully evaluated GNN encoder for true graph-based DERG reasoning
- Add human annotations for trust actions
- Rerun OpenSOC-AI and external baselines under the same evaluation harness
- Integrate real-time CTI feeds for temporal analysis validation

## Citation

Citation placeholder for the future paper.
------
Copyright: To Duy Tai
