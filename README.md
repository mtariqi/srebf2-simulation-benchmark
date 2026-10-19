# SREBF2 Simulation Benchmark

## Project Objective

Develop reproducible computational simulations to
evaluate RNA-seq differential-expression methods,
genotype-by-environment interactions, statistical
power, and exploratory epigenomic analysis.
```
flowchart TB
```
    A["HepG2 cells<br/>pooled siRNA transfection<br/>n = 4 independent replicates per condition"]
    A --> B1["NTC siRNA<br/>control"]
    A --> B2["siSREBF2<br/>knockdown"]

    B1 --> V{"Knockdown validation<br/>qRT-PCR + Western blot<br/>(precursor vs nuclear SREBP2)"}
    B2 --> V
    V -- "inadequate" --> R["Re-optimize transfection<br/>or exclude replicate"]
    R -.-> B2
    V -- "pass" --> S["Matched sister cultures<br/>single harvest at ~72 h<br/>identical sterol context"]

    S --> T["<b>Aim 1</b><br/>Transcriptomics: RNA-seq<br/>counts → DESeq2 + pathway enrichment"]
    S --> E["<b>Aim 1</b><br/>Epigenomics: CUT&RUN<br/>SREBP2 occupancy (peaks), IgG control"]
    S --> L["<b>Aim 2</b><br/>Lipidomics: targeted LC-MS<br/>free cholesterol, CE species, precursors"]
    S --> PH["<b>Aim 2</b><br/>Phenomics: high-content imaging<br/>LDL uptake, neutral lipids, morphology"]

    T --> I["<b>Integration</b><br/>pathway-level expression vs occupancy<br/>vs lipid and phenotype changes"]
    E --> I
    L --> I
    PH --> I

    I --> SUP["<b>Supports hypothesis</b><br/>coordinated target-gene downregulation<br/>+ reduced CE / precursors + phenotype"]
    I --> OPP["<b>Argues against / qualifies</b><br/>unchanged genes or lipids →<br/>compensation, timing, or assay limits"]
```
## Research Approach

1. Generate synthetic RNA-seq count matrices.
2. Introduce known differential-expression effects.
3. Simulate genotype-by-serum interactions.
4. Evaluate DESeq2 sensitivity and false discoveries.
5. Assess sample-size and dispersion effects.
6. Develop simulated CUT&Tag signal benchmarks.

## Scientific Integrity & Repository Reference

Integrity Notice: All datasets generated within this benchmark are strictly synthetic. Simulated results are used exclusively for method validation, workflow optimization, and pipeline robustness testing—never as experimental evidence of biological SREBF2 regulation.

