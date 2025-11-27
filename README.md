# MMXU benchmark
**MMXU** (Multimodal and MultiX-ray Understanding) is a novel dataset for MedVQA that focuses on identifying changes in specific regions between two patient visits. Unlike previous datasets that primarily address single-image questions, MMXU enables multi-image questions, incorporating both current and historical patient data. 

[![Paper](https://img.shields.io/badge/paper-available-brightgreen)](https://arxiv.org/pdf/2502.11651) [![huggingface](https://img.shields.io/badge/huggingface-available-yellow)](https://huggingface.co/datasets/LinjieMu/MMXU) [![github](https://img.shields.io/badge/github-available-blue)](https://github.com/LinjieMu/MMXU)

## News

- (05/16/2025) Our [paper](https://arxiv.org/pdf/2502.11651) has been accepted by ACL 2025 Findings!
- (02/22/2025) The MMXU-test benchmark has been released, containing 3,000 multiple-choice questions on disease progression in chest X‑rays!

## Table of Contents
- [MMXU benchmark](#mmxu-benchmark)
  - [News](#news)
  - [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Usage](#usage)
- [Case Example](#case-example)
- [Citation](#citation)

# Introduction

In this paper, we introduce MMXU (Multimodal and MultiX-ray Understanding), leveraging the rich resources of patient electronic medical records (EMRs) from the MIMIC-CXR dataset. Unlike previous works, which focus solely on the current image or are restricted to simple questions, this benchmark is specifically designed to inquire about differences in specific regions between a patient’s two visits. MMXU contains two splits: *test* and *dev*. `MMXU-test` consists of 3,000 entries from 1,201 patients and 2,469 studies, while `MMXU-dev` contains 118K QA pairs involving 114K images. 

![MMXU pipeline](imgs/framework.png)

The figure outlines the pipeline for constructing MMXU. The process begins with the Chest ImaGenome dataset. The entire method comprises four distinct phases:

1. Comparative Sentence Extraction
2. Comparative Target Selection
3. QA Pair Generation
4. Post‑Processing

# Usage
* **File description**

  * `MMXU-test.jsonl`: the MMXU test split, containing 3 k examples.
  * `MMXU-dev.jsonl`: the MMXU development/training split, containing 118 k examples. **Due to PhysioNet restrictions, we cannot release the dev data publicly. If you would like to contact us further regarding this, please feel free to email me at linjiemu@sjtu.edu.cn.**

* **Data Description**

  Each entry in the `MMXU-dev.jsonl` files contains the following fields:

  - `id`: A unique numerical identifier for each data entry.
  - `content_type`: The category of the question, often indicating the type of change being assessed.
  - `related_region_name`: The specific anatomical area of interest in the medical image.
  - `question`: The specific question that needs to be answered by comparing the current and prior medical images/reports.
  - `options`: A dictionary of possible multiple-choice answers to the question.
  - `answer`: The key corresponding to the correct option.
  - `explanation`: A text-based justification for why the answer is correct, often referencing the medical reports.
  - `cur_image_path`: The file path to the most recent medical image.
  - `cur_report`: The complete radiologist's report corresponding to the `cur_image_path`.
  - `cur_region_report`: A specific snippet from the full report that describes the findings in the `related_region_name`.
  - `cur_image_bboxs`: A dictionary containing the bounding box coordinates (`[x_min, y_min, x_max, y_max]`) for anatomical regions in the current image.
  - `prior_image_path`: A list containing file paths to one or more previous images used for comparison.
  - `prior_report`: The complete radiologist's report for the prior image(s).
  - `prior_image_bboxs`: Bounding box coordinates for regions in the prior image. **It can be empty if the region was not annotated previously.**

* **Images**

  * Please apply for and download the MIMIC‑CXR‑JPG dataset from [https://physionet.org/content/mimic-cxr-jpg/2.1.0/](https://physionet.org/content/mimic-cxr-jpg/2.1.0/).
  * After downloading, either create a symbolic link from this project’s `files` directory to the `files` directory of the MIMIC‑CXR‑JPG dataset, or adjust the image paths accordingly.


* **Report information**

  * Our dataset is built on the MIMIC‑CXR‑JPG dataset, which is a restricted‑access resource. This means we cannot release the associated report content elsewhere.

# Case Example

![MMXU example](imgs/case.png)

# Citation
If you use the `MMXU dataset` in your research, please cite the following paper:

```bibtex
@article{mu2025mmxu,
  title={MMXU: A Multi-Modal and Multi-X-ray Understanding Dataset for Disease Progression},
  author={Mu, Linjie and Huang, Zhongzhen and Qin, Shengqian and Zhu, Yakun and Zhang, Shaoting and Zhang, Xiaofan},
  journal={arXiv preprint arXiv:2502.11651},
  year={2025}
}
