# Metrics and Protocols

VLM-grounded industrial anomaly detection papers often report similar metric names under different evidence settings. This page keeps the main distinctions explicit.

## Metrics

| Metric | Typical level | What it measures | Caution |
| --- | --- | --- | --- |
| AC | image level | anomaly classification AUROC | does not establish localization quality |
| AS | pixel level | anomaly segmentation AUROC | can reward good ranking without coherent defect-region coverage |
| PRO | region level | per-region overlap under false-positive constraints | better reflects connected defect coverage |
| AP | pixel or instance level | precision-recall behavior under class imbalance | sensitive to threshold and positive-area ratio |
| F1 | image, pixel, or reasoning level | thresholded precision-recall trade-off | depends strongly on threshold selection |
| Accuracy | reasoning or classification | correctness of labels or answers | may hide class imbalance and grounding errors |

## Protocol Labels

| Label | Evidence allowed at inference | Typical methods |
| --- | --- | --- |
| Single-image zero-shot | the inspected image and fixed text prompts | prompt-only CLIP scoring, simple VLM scoring |
| Context-enhanced zero-shot | the inspected image plus unlabeled context or online stream context | MuSc, RareCLIP-style context or memory |
| Few-normal-shot | limited normal support images for the target category | WinCLIP few-shot, PromptAD, adapter or prototype methods |
| Adapted CLIP or VLM | prompt, adapter, or projection parameters updated before inference | AnomalyCLIP, AdaCLIP, AA-CLIP |
| Auxiliary-prior fusion | masks, 3D views, frequency features, DINO features, or other priors | CLIP-SAM, PointAD, FE-CLIP, S2SWCLIP |
| Reasoning-level inspection | generated text, retrieved knowledge, logic rules, or tool calls | AnomalyGPT, MMAD, LogicAD, AgentIAD |

## Reporting Rules

- Do not rank methods only by a single number if their evidence protocols differ.
- Report the backbone, input resolution, support budget, memory budget, prompt count, sampling count, and whether context features are precomputed.
- Keep image-level, pixel-level, region-level, and reasoning metrics separate.
- For ablations, identify whether the component is removed in isolation or only as part of a coupled pipeline.
- For computational cost, report hardware, latency unit, batch size, memory, and whether preprocessing or support features are cached.
