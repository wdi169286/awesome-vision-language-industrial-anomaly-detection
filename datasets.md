# Datasets

This page records the main datasets used by VLM-grounded industrial anomaly detection papers. The goal is not only to list datasets, but to clarify what kind of inspection evidence each benchmark stresses.

## Core VLM-IAD Benchmarks

| Dataset | Year | Scale | Modality | Annotation | What it tests |
| --- | --- | --- | --- | --- | --- |
| MVTec AD | 2019 | 15 classes, 5,354 images | RGB | pixel masks | canonical object and texture defects under controlled acquisition |
| VisA | 2022 | 12 classes, 10,821 images | RGB | pixel masks | larger category and appearance diversity for RGB inspection |
| MVTec LOCO AD | 2022 | 5 classes, 3,340 images | RGB | pixel masks and logical anomaly setting | structural and logical anomalies beyond local surface defects |
| MVTec 3D-AD | 2021 | 10 classes, 3,852 samples | RGB and 3D | pixel or point-level localization | geometry-aware inspection with depth or point evidence |
| Real-IAD | 2024 | 30 classes, 151,050 images | RGB multi-view | pixel masks | large-scale real-world multi-view industrial inspection |
| Real-IAD MVN | 2026 | multi-view normal-vector benchmark | multi-view RGB and normal vectors | high-fidelity localization | surface-normal and multi-view geometric evidence |
| MMAD | 2025 | multimodal industrial anomaly benchmark | images, text, and reasoning-oriented queries | answer and reasoning labels | MLLM anomaly understanding and explanation |

## Useful Transfer and Stress-Test Datasets

These datasets are not always central in VLM-IAD papers, but they are useful for testing whether a method generalizes beyond the standard MVTec AD and VisA setting.

| Dataset | Modality | Annotation | Why it may be useful |
| --- | --- | --- | --- |
| BTAD | RGB | pixel masks | small real-world benchmark for localization robustness |
| MPDD / MPDD2 | RGB | pixel masks | metal-part inspection under more complex acquisition conditions |
| DAGM | RGB synthetic | defect masks | controlled synthetic texture defects |
| KolektorSDD / KolektorSDD2 | RGB | pixel masks | surface-defect segmentation with limited categories |
| NEU Surface Defect | RGB | bounding boxes or class labels | steel surface defect recognition and classification |
| DeepPCB | RGB | bounding boxes | PCB defect detection with structured manufactured patterns |
| GDXray | X-ray | bounding boxes | nondestructive testing and industrial X-ray inspection |
| Eyecandies | RGB-D synthetic | pixel masks | multimodal anomaly localization with synthetic geometry and appearance |
| Real3D-AD | point cloud | point-level masks | real 3D point-cloud anomaly detection |
| MVTec AD 2 | RGB | pixel masks | advanced unsupervised anomaly detection scenarios |

## Emerging Benchmarks to Track

These newer benchmarks are useful to track because they move closer to VLM-IAD questions such as visual-text grounding, multilevel reasoning, multi-sensor evidence, tiny-object inspection, and larger real-world coverage. They should be verified carefully before being used in result tables.

| Dataset or benchmark | Focus |
| --- | --- |
| MVTec-Caption | anomaly-related image captioning and multimodal synthesis |
| MANTA | multi-view and visual-text anomaly detection for tiny objects |
| MMAD | MLLM-based industrial anomaly understanding |
| MMR-AD | large-scale multimodal anomaly benchmark for MLLMs |
| M3-AD | reflection-aware multimodal and multidimensional industrial anomaly benchmark |
| Real-IAD D3 | real-world 2D, pseudo-3D, and 3D anomaly detection |
| Multi-Sensor Object Anomaly Detection | appearance, geometry, and internal-property fusion |
| Defect Spectrum | semantic-rich large-scale defect dataset |
| Are Anomaly Scores Telling the Whole Story? | multilevel anomaly evaluation beyond a single score |

## Dataset Notes

- RGB datasets are still useful for benchmarking semantic prompting and dense localization, but they do not fully test process-aware or reasoning-based inspection.
- Multi-view, 3D, and normal-vector datasets are important for defects where shape and assembly state matter more than texture alone.
- Reasoning-oriented benchmarks should report not only the final answer, but also whether the explanation is grounded in the abnormal region or retrieved industrial knowledge.
- When reporting results, include the evidence setting. A method using only the test image, a method using support images, and a method using the whole unlabeled test set are not the same benchmark protocol.
- Watchlist datasets are not automatically comparable with MVTec AD or VisA. They should be used to test a specific capability such as tiny-object reasoning, multiview geometry, process evidence, or visual-text explanation.

## Benchmark Links

- [MVTec AD](https://www.mvtec.com/company/research/datasets/mvtec-ad)
- [MVTec LOCO AD](https://www.mvtec.com/company/research/datasets/mvtec-loco)
- [MVTec 3D-AD](https://www.mvtec.com/company/research/datasets/mvtec-3d-ad)
- [Real-IAD](https://realiad4ad.github.io/Real-IAD/)
- [MVTec AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-ad)
- [VisA on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-visa)
- [MVTec LOCO AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-loco-ad)
- [MVTec 3D-AD on Papers with Code](https://paperswithcode.com/sota/anomaly-detection-on-mvtec-3d-ad)
