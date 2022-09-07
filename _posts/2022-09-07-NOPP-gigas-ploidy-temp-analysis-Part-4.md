---
layout: post
title: Wed. Sept. 07, 2022
subtitle: NOPP-gigas-ploidy-temp analysis - Part 4
gh-repo: mattgeorgephd/mattgeorge.github.io
gh-badge: [star, fork, follow]
tags: NOPP-gigas-ploidy-temp TagSeq
comments: true
---

Project name: [NOPP-gigas-ploidy-temp](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp) <br />
Funding source: [National Oceanographic Partnership Program](https://www.nopp.org/) <br />
Species: *Crassostrea gigas* <br />
variable: ploidy, elevated seawater temperature, desiccation <br />
Github repo: [NOPP-gigas-ploidy-temp](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp)

[<< previous notebook entry <<](https://mattgeorgephd.github.io/NOPP-gigas-ploidy-temp-analysis-Part-3/)
 |
[>> next notebook entry >>](https://mattgeorgephd.github.io/NOPP-gigas-ploidy-temp-analysis-Part-5/)

## Tagseq analysis - Generate Gene Tables
Using the following [R script](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/scripts/3_generate_gene_tables.Rmd):
1. I imported the significant (p<0.05, lfc>1.5) genes generated from DESeq2 using the apeglm shrinkage estimator for each comparison,
2. sorted by whether the LOCID were characterized or uncharacterized, and
3. generated gene tables w/ descriptions

Here are the results:

**VOLCANO PLOTS: Multiple comparisons by treatment**

| comparison | control | single-stressor | multi-stressor |
| :---:  | :---: | :---: | :---: |
| ploidy | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/control_ploidy/Volcano_sig_genes_apeglm.png?raw=true) | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/heat_ploidy/Volcano_sig_genes_apeglm.png?raw=true) | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/desiccation_ploidy/Volcano_sig_genes_apeglm.png?raw=true) |

**VOLCANO PLOTS: significant genes by ploidy**

|  comparison | diploid | triploid |
|:---:|:---:|:---:|
|single-stressor v control   | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/diploid_heat/Volcano_sig_genes_apeglm.png?raw=true)  | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_heat/Volcano_sig_genes_apeglm.png?raw=true)  |
|multi-stressor v control    | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_heat/Volcano_sig_genes_apeglm.png?raw=true)  | ![](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/main/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_desiccation/Volcano_sig_genes_apeglm.png?raw=true)  |

**DEG LISTS: summary stats**

About half of the LOCIDs associated with the DEGS were unknown within each comparison (SS = single stressor; MS = multi-stressor)

| ploidy | treatment | known | unknown | percent_unknown |
|:---: |:---:|:---:|:---:| :---:|
| both | control v control  | 44 | 65 | 0.60 |
| both | SS v SS | 182 | 161  | 0.469 |
| both | MS v MS  | 60  | 78  | 0.565 |
| diploid  | SS v control  | 174  | 142  | 0.45 |
| diploid  | MS v control  | 45  | 27  | 0.375 |
| triploid | SS v control  | 59  | 33  | 0.36 |
| triploid | MS v control | 40 | 22  | 0.35 |

**DEG LISTS: links to lists**

Links to lists of all and significant DEGs. SS = single stressor; MS = multi-stressor.

| ploidy | treatment | DEG_all | DEG_sig |
|:---: |:---:|:---:|:---:|
| both     | control v control  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/control_ploidy/CONTROL_PLOIDY-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/control_ploidy/CONTROL_PLOIDY-SIG-DEG-apeglm.csv)  |
| both     | SS v SS            | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/heat_ploidy/HEAT_PLOIDY-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/heat_ploidy/HEAT_PLOIDY-SIG-DEG-apeglm.csv)  |
| both     | MS v MS            | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/desiccation_ploidy/DESICCATION_PLOIDY-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/desiccation_ploidy/DESICCATION_PLOIDY-SIG-DEG-apeglm.csv)  |
| diploid  | SS v control       | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/diploid_heat/DIPLOID_HEAT-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/diploid_heat/DIPLOID_HEAT-SIG-DEG-apeglm.csv)  |
| diploid  | MS v control       | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/diploid_desiccation/DIPLOID_DESICCATION-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/diploid_desiccation/DIPLOID_DESICCATION-SIG-DEG-apeglm.csv)  |
| triploid | SS v control       | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_heat/TRIPLOID_HEAT-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_heat/TRIPLOID_HEAT-SIG-DEG-apeglm.csv)  |
| triploid | MS v control       | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_desiccation/TRIPLOID_DESICCATION-ALL-DEG-apeglm.csv)  | [X](https://github.com/mattgeorgephd/NOPP-gigas-ploidy-temp/blob/ad15d2e309a2ffdd1ccb8c71c3fc1eb7b328b0a0/202107_EXP2/tag-seq/output/filtered/HISAT2_multiqc_biplot/triploid_desiccation/TRIPLOID_DESICCATION-SIG-DEG-apeglm.csv)  |

**DAVID: GOterm analysis**
