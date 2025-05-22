# MMXU benchmark
**MMXU** (Multimodal and MultiX-ray Understanding) is a novel dataset for MedVQA that focuses on identifying changes in specific regions between two patient visits. Unlike previous datasets that primarily address single-image questions, MMXU enables multi-image questions, incorporating both current and historical patient data. 

[![Paper](https://img.shields.io/badge/paper-available-brightgreen)](https://arxiv.org/pdf/2502.11651)

## News

- (05/16/2025) Our [paper](https://arxiv.org/pdf/2502.11651) has been accepted by ACL 2025 Findings!
- (02/22/2025) The MMXU-test benchmark has been released, containing 3,000 multiple-choice questions on disease progression in chest X‑rays!
 
## Table of Contents
- [MMXU benchmark](#mmxu-benchmark)
  - [News](#news)
  - [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Citation](#citation)

# Introduction

In this paper, we introduce MMXU (Multimodal and MultiX-ray Understanding), leveraging the rich resources of patient electronic medical records (EMRs) from the MIMIC-CXR dataset. Unlike previous works, which focus solely on the current image or are restricted to simple questions, this benchmark is specifically designed to inquire about differences in specific regions between a patient’s two visits. MMXU contains two splits: *test* and *dev*. `MMXU-test` consists of 3,000 entries from 1,201 patients and 2,469 studies, while `MMXU-dev` contains 118K QA pairs involving 114K images. 

![MMXU pipeline](imgs/framework.png)

The figure outlines the pipeline for constructing MMXU. The process begins with the Chest ImaGenome dataset. The entire method comprises four distinct phases:

1. Comparative Sentence Extraction
2. Comparative Target Selection
3. QA Pair Generation
4. Post‑Processing




# Citation
If you use the `MMXU dataset` in your research, please cite the following paper:

```bibtex
@article{mu2025mmxu,
  title={MMXU: A Multi-Modal and Multi-X-ray Understanding Dataset for Disease Progression},
  author={Mu, Linjie and Huang, Zhongzhen and Qin, Shengqian and Zhu, Yakun and Zhang, Shaoting and Zhang, Xiaofan},
  journal={arXiv preprint arXiv:2502.11651},
  year={2025}
}
```