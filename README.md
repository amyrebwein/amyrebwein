# Amy Weiner

Software engineer → ML engineer for health tech. First-year MS student in Biomedical Informatics and Data Science at **Johns Hopkins School of Medicine** (expected May 2028), after ~10 years at San Francisco startups (including Udemy) in infrastructure and engineering management.

This profile documents that transition in public, so expect early-stage work that gets more polished over time.

## Currently

- **Research rotation** with Dr. Blake Dewey: how MRI resolution affects FreeSurfer brain measurements
- **Coursework:** SQL on de-identified EHR data, clinical data analysis in Python, biostatistics in R
- **Habits:** tests, type hints, packaging and CI on everything I push here

## Research: MRI resolution and brain measurements

Research brain MRI uses thin 1 mm slices; routine clinical scans often use 5 mm or more. Tools like FreeSurfer, including the newer [recon-all-clinical](https://arxiv.org/abs/2409.03889), turn scans into brain volumes and cortical thickness. I'm measuring how much thick slices shift those numbers, and whether the software signals a problem when they do.

<details>
<summary><b>Approach, engineering and tools</b></summary>

### Questions
1. When slices get thicker, how much do volumes and thickness shift, compared with repeat-scan variation? Is the shift the same for every structure?
2. When the input is degraded, does the software flag it, or return a plausible number anyway?

### Approach
- **Simulate, don't rescan:** degrade high-resolution scans to 3 mm and 5 mm + 1 mm gap, so only resolution changes
- **Two pipelines:** FreeSurfer `recon-all` and `recon-all-clinical` (SynthSeg, SynthSR, SynthDist)
- **Consistency, not accuracy:** each result vs. the same person's 1 mm result, same pipeline
- **Bias vs. noise:** compare shifts with scan-rescan variation from a public OpenNeuro traveling-subject dataset
- **Next:** cortical thickness, quality-score checks, longitudinal effects

### Engineering
- Reproducible environment: conda + FreeSurfer 8.2 in Apptainer, setup check before each session
- Numbered pipeline; each step reruns on its own
- Idempotent jobs: completion markers, rerun-failures-only, dry-run mode
- Dated research log and weekly sprint board
- Study images never leave the secure server; only code goes to GitHub

### Tools
FreeSurfer · radifox-utils · Apptainer · Python (nibabel, NumPy, pandas, matplotlib) · R (dplyr, ggplot2) · Bash · Git

**Status:** pipeline running, analysis in progress. Code private for now.

</details>

## Roadmap

| When | Focus |
| --- | --- |
| Winter–spring 2027 | Second research rotation; ML fundamentals, PyTorch, deep learning for medical imaging, experiment tracking |
| Summer 2027 | Thesis research begins; internship if I can land one |
| 2027–2028 | Model deployment and monitoring, computer vision for health tech |

## Tech

**Professional:** Python · SQL · MySQL · Redis · Terraform · Ansible · Kubernetes · Docker · CI/CD<br>
**Learning:** pandas · NumPy · R · FreeSurfer · nibabel · OMOP/OHDSI<br>
**Next:** PyTorch · MONAI · scikit-learn · MLflow · FastAPI

## Data

Public repos use only public, de-identified or synthetic data. Patient and study data stays inside approved Hopkins environments.

## Contact

[LinkedIn](https://www.linkedin.com/in/amyrweiner) · amyrebwein@gmail.com
