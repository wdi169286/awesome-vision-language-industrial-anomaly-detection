# Roadmap

This repository starts as a taxonomy-aware companion list for the survey. The next steps should make it easier to maintain and reuse.

## Near Term

- Fill verified paper URLs and official code URLs in `data/papers.yml`.
- Add a compact "recent updates" section to `README.md` after each batch update.
- Add venue tags and official arXiv IDs where available.
- Mark papers with code, no code, or unofficial implementation.
- Verify watchlist datasets from community resources before promoting them to core benchmark tables.

## Medium Term

- Generate `papers.md` from `data/papers.yml` to avoid manual drift.
- Add a timeline figure for VLM-grounded IAD methods.
- Add a taxonomy tree figure matching the companion survey.
- Add result tables only when dataset, metric, protocol, and source table are all clear.
- Add dataset filters for RGB, RGB-D, 3D, X-ray, visual-text, MLLM reasoning, and multi-sensor inspection.

## Long Term

- Build a small static website from the YAML catalogue.
- Add filters for evidence role, protocol, dataset, modality, and code availability.
- Maintain a changelog for newly added papers and corrected protocol notes.
