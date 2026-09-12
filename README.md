<div align="center">

<img src="https://alphaleporus.github.io/gsoc-2026-gprmax/assets/bscan-live.gif" alt="A ground-penetrating radar B-scan assembling trace by trace while the gprMax solver writes it, the reflection hyperbola of a buried cylinder emerging as the antenna advances." width="100%">

<sub>A radargram assembling itself trace by trace while the solver writes it. The hyperbola is a metal cylinder buried in a dielectric half-space.<br>Built for Google Summer of Code 2026.</sub>

<br><br>

<a href="https://summerofcode.withgoogle.com/"><img src="https://alphaleporus.github.io/gsoc-2026-gprmax/assets/gsoc-logo.png" height="46" alt="Google Summer of Code"></a>
&nbsp;&nbsp;&nbsp;
<a href="https://github.com/gprMax/gprMax"><img src="https://alphaleporus.github.io/gsoc-2026-gprmax/assets/gprmax-logo.png" height="46" alt="gprMax"></a>
&nbsp;&nbsp;&nbsp;
<a href="https://marimo.io"><img src="https://alphaleporus.github.io/gsoc-2026-gprmax/assets/marimo-logo.svg" height="40" alt="marimo"></a>

# Gaurav Sharma

**Inverse problems and scientific ML.** Mostly Python, some Java.

[![Project site](https://img.shields.io/badge/GSoC_2026-write--up-0a3a30?style=flat-square)](https://alphaleporus.github.io/gsoc-2026-gprmax/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-alphaleporus-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alphaleporus/)
[![X](https://img.shields.io/badge/X-@alphaleporus-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/alphaleporus)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0007--8027--9943-A6CE39?style=flat-square&logo=orcid&logoColor=white)](https://orcid.org/0009-0007-8027-9943)
[![LeetCode](https://img.shields.io/badge/LeetCode-alphaleporus-FFA116?style=flat-square&logo=leetcode&logoColor=white)](https://leetcode.com/alphaleporus)

</div>

---

### Google Summer of Code 2026 · [gprMax](https://github.com/gprMax/gprMax)

Reactive Simulation and Analytics: integrating [marimo](https://marimo.io) with gprMax, an FDTD solver for ground-penetrating radar. Mentored by Prof. Antonis Giannopoulos and Prof. Craig Warren at the University of Edinburgh, with Iraklis Giannakis, Zach Wilson and Petroula Karacosta.

Looking at gprMax output used to mean editing a text file, re-running the solver from a terminal, and running a matplotlib script that decided for you what to show. That loop is now six reactive notebooks and four pure-Python modules.

| | |
|---|---|
| **6** notebooks | parameter controls, live progress tracking, A-scan and B-scan dashboards, two recipe workflows |
| **4** modules | HDF5 reading, radargram assembly, six gain forms and background removal, hyperbola travel-time modelling |
| **156** tests | 99% coverage on the four modules, guards mutation-tested rather than assumed |
| **7** PRs | open against `gprMax:devel` |
| **3** bugs | found in gprMax's existing plotting and progress code |

<div align="center">
<img src="https://alphaleporus.github.io/gsoc-2026-gprmax/assets/recipe-velocity.gif" alt="Loading a B-scan and sliding a predicted hyperbola onto the reflection until the slider reads out the permittivity." width="88%">
<br><sub>Move the slider until the predicted hyperbola sits on the reflection, and the slider is telling you the permittivity.</sub>
</div>

The findings stand whether or not any notebook merges. `fft_power` silently normalises every trace against its own peak, so two traces twenty times apart in amplitude plot identically when overlaid. A view fallback in `plot_Ascan.py` applies a frequency value as an array index and runs past the end. The ricker source delay is 31% of the standard time window and is not recoverable from the output file, so any predicted arrival that omits it is wrong by a third of the plot.

Depth and permittivity turn out not to be jointly recoverable from a hyperbola fit. The velocity recipe takes depth as an input and says why, rather than reporting a number it cannot support. A tool that quietly tunes itself toward the expected answer is worse than no tool.

**[Full write-up, figures and validation →](https://alphaleporus.github.io/gsoc-2026-gprmax/)**  ·  [source](https://github.com/alphaleporus/gsoc-2026-gprmax)

---

### Now

**Still on gprMax.** Bandpass and lowpass filters, noise injection, B-scan subtraction, a VTKHDF geometry viewer, and the Apple Silicon build fix as its own PR.

**Preprocessing and corruption robustness in medical vision transformers.** How CLAHE affects MedViT V1 and V2 across the MedMNIST benchmark suite. Write-up in progress.

**Forecasting metrics and performance in [sktime](https://github.com/sktime/sktime)**, plus upstream bug reports against marimo for reactive DAG issues found during GSoC.

**Bitcoin protocol development** through Bitshala's Mastering Bitcoin cohort.

---

### Selected work

| Project | |
|---|---|
| **OsteoVision** | EfficientNet-B0 imaging branch fused with a tabular MLP for clinical risk prediction. AUC-ROC 0.972, per-class threshold tuning, MC Dropout for uncertainty. Built at the AesCode Nexus MedTech Hackathon. |
| **Tooth-AI** | Automated dental OPG analysis, Mask R-CNN instance segmentation with FDI tooth numbering. Under Prof. Nisha Auti through the C-CAMP Inter-Institutional Biomedical Innovations Programme. Paper in preparation. |
| **FleetFusion** | First place, GenAIverse national hackathon. |

---

### Open source

| Project | Merged | Open |
|---|---|---|
| [sktime](https://github.com/sktime/sktime) | [#9140](https://github.com/sktime/sktime/pull/9140), [#9095](https://github.com/sktime/sktime/pull/9095), [#9086](https://github.com/sktime/sktime/pull/9086) — MAAPE and MSLE metrics, `NaiveForecaster` docs | [#9295](https://github.com/sktime/sktime/pull/9295) performance |
| [mllam/neural-lam](https://github.com/mllam/neural-lam) | [#428](https://github.com/mllam/neural-lam/pull/428), [#442](https://github.com/mllam/neural-lam/pull/442) — Sphinx autodoc harness | |
| [Jenkins](https://github.com/jenkinsci) | #1381 — ARM64 CI/CD fix | |
| [gprMax](https://github.com/gprMax/gprMax) | | [seven PRs](https://alphaleporus.github.io/gsoc-2026-gprmax/#pull-requests) from GSoC 2026 |
| [OpenML](https://github.com/openml/openml-python) | | [#1490](https://github.com/openml/openml-python/pull/1490) |

---

<div align="center">

`Python` · `Java` · `PyTorch` · `NumPy` · `SciPy` · `scikit-learn` · `marimo` · `Plotly` · `HDF5` · `pytest` · `Docker`

<sub>Third-year Computer Engineering at Bharati Vidyapeeth College of Engineering, Pune. Graduating 2027.<br>
Technical Head at CSI Bharati Vidyapeeth (250 students), Media &amp; Cultural Head at ACES.</sub>

</div>
