# waste-domain-generalization
# Leakage-Controlled Multi-Source Domain Generalization for Waste Classification

This repository contains the code, manifests, derived results, statistical
analysis, and figure-generation materials supporting the associated study.

## Confirmatory design

Five ResNet50 configurations were evaluated using five common seeds:

- B0: Standard ResNet50
- B1: Domain-robust augmentation
- B2: Global CORAL
- B3a: Balanced sampling
- B3b: Memory-bank class-conditional CORAL

Seeds: 42, 123, 2026, 3407, and 5891.

The final method was selected using five-seed mean RealWaste macro-F1.
B2 Global CORAL was frozen before the one-time external TrashBox evaluation.

## Dataset roles

- Source training: 8,442 images
- Source validation: 1,492 images
- RealWaste development benchmark: 3,587 images
- Sealed external TrashBox evaluation: 2,344 images from five matched classes

Dataset images are not redistributed in this repository. Users must obtain
each dataset from its original provider and comply with the applicable terms.

## B3b memory-bank audit

B3b uses detached historical memory features and non-detached current
features. The executed automatic-differentiation audit verified a finite,
nonzero gradient from the memory-bank class-conditional CORAL loss to the
current backbone features.

See:

`result/b3b_gradient_verification.json`

## Reproducibility

The repository provides:

- Frozen experiment configurations
- Common random seeds
- Ontology mappings
- Leakage and exclusion summaries
- Five-seed metrics
- Per-image prediction outputs where permitted
- Paired and hierarchical statistical analysis
- External evaluation summaries
- B3b gradient-path verification

## Data availability and licensing

The original images are not redistributed. Dataset provenance and licensing
information are recorded in:

`manifest/dataset_license_audit.csv`

## Citation

Please cite the associated article and the original dataset publications.
