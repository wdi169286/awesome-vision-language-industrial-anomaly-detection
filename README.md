# Awesome VLM-Grounded Industrial Anomaly Detection

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blue)

A curated resource for vision-language and multimodal foundation-model research in zero-shot and few-shot industrial anomaly detection.

This repository is maintained as a companion resource for our survey on VLM-grounded industrial anomaly detection. It organizes papers by the role that each method plays in constructing inspection evidence, rather than only by year, venue, or backbone.

## Scope

Industrial anomaly detection with vision-language models is no longer only a question of image-level scoring. Recent methods use semantic prompts, dense image-text alignment, scarce normal references, memory banks, auxiliary foundation priors, 3D or frequency evidence, and reasoning modules. This list is designed to make those differences visible.

We focus on work that is relevant to:

- zero-shot, few-shot, or scarce-evidence industrial anomaly classification and segmentation
- CLIP, VLM, LVLM, MLLM, or other foundation-model based inspection
- multimodal industrial anomaly detection with language, 3D, frequency, mask, memory, or reasoning evidence
- benchmark protocols, datasets, metrics, and deployment evidence for VLM-IAD

## Contents

- [Taxonomy](#taxonomy)
- [Core Reading](#core-reading)
- [Recommended Benchmark Entry Points](#recommended-benchmark-entry-points)
- [Repository Files](#repository-files)
- [Benchmarks and Protocols](#benchmarks-and-protocols)
- [Contributing](#contributing)
- [Citation](#citation)

## Taxonomy

The list follows a primary-role taxonomy from the survey.

| Role | What it contributes | Typical evidence operation |
| --- | --- | --- |
| Semantic prior construction | Defines normal and abnormal states through language or prompt learning | state prompts, hybrid prompts, uncertainty sampling, prompt mixtures |
| Cross-modal local evidence | Converts image-text alignment into spatial anomaly maps | window scoring, patch-text matching, dense projection, high-resolution alignment |
| Scarce-sample calibration | Uses limited normal evidence to recalibrate foundation-model scores | support images, prototypes, adapters, memory or retrieval |
| Auxiliary foundation-prior coupling | Adds complementary priors beyond a single RGB-text branch | SAM masks, DINO features, 3D views, frequency or wavelet evidence |
| Reasoning-level inspection | Produces or evaluates inspection claims with language reasoning | LVLM dialogue, knowledge retrieval, logic rules, agentic tools |

## Core Reading

- [Papers by taxonomy](papers.md)
- [Datasets](datasets.md)
- [Metrics and protocols](metrics-and-protocols.md)
- [Machine-readable catalogue](data/papers.yml)
- [Maintenance roadmap](ROADMAP.md)

## Recommended Benchmark Entry Points

These benchmark links are useful starting points before comparing papers.

| Benchmark | Use case |
| --- | --- |
| [MVTec AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-ad) | common RGB anomaly classification and segmentation reference |
| [VisA on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-visa) | multi-category RGB anomaly detection reference |
| [MVTec LOCO AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-loco-ad) | logical and structural anomaly reference |
| [MVTec 3D-AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-3d-ad) | 3D and RGB-D anomaly detection reference |

## Repository Files

| File | Purpose |
| --- | --- |
| `README.md` | Entry point and taxonomy overview |
| `papers.md` | Curated paper list grouped by evidence role |
| `datasets.md` | Industrial anomaly datasets and what they test |
| `metrics-and-protocols.md` | Metric definitions and protocol cautions |
| `data/papers.yml` | Structured catalogue for future scripts and website export |
| `data/datasets.yml` | Structured dataset catalogue |
| `CONTRIBUTING.md` | Rules for adding papers, code links, and protocol notes |
| `ROADMAP.md` | Maintenance plan for links, code, timelines, and result tables |

## Benchmarks and Protocols

When adding results, please keep the protocol visible. Image-level AUROC, pixel-level AUROC, PRO, AP, and reasoning accuracy are not interchangeable. Zero-shot single-image inference, online context, memory-assisted inference, few-normal-shot adaptation, and LVLM reasoning should not be ranked as if they used the same evidence.

## Contributing

Pull requests are welcome. Please follow [CONTRIBUTING.md](CONTRIBUTING.md) and include the paper title, year, venue, taxonomy role, inspection setting, dataset, metric, code link if available, and a short protocol note.

## Citation

If this repository is useful for your work, please cite the companion survey once the final bibliographic information is available. The BibTeX entry will be added after publication.

## Related Resource

This repository is inspired by community-maintained awesome lists such as [M-3LAB/awesome-industrial-anomaly-detection](https://github.com/m-3lab/awesome-industrial-anomaly-detection), but narrows the organization to VLM-grounded and multimodal foundation-model based IAD.
