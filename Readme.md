# INF605 Final Project: Zhang-Suen Parallel Thinning Algorithm

This repository contains the implementation, theoretical analysis, and experimental evaluation of the **Zhang-Suen Fast Parallel Thinning Algorithm**
for the **INF605 Image Processing and Computer Vision** course at Türk-Alman Üniversitesi.

---

## 👥 Project Team (Group 9)

| Name | Student ID | Email | Role / Contribution |
| :--- | :--- | :--- | :--- |
| **Emre Berkay Güntekin** | 250503069 | e250503069@stud.tau.edu.tr
| **Kerem Özdemir** | 220503048 | e220503048@stud.tau.edu.tr 
| **Mustafa Kaya** | 200503020 | e200503020@stud.tau.edu.tr 
---

## 📚 Paper Reference
* **Title:** A fast parallel algorithm for thinning digital patterns
* **Authors:** T. Y. Zhang and C. Y. Suen
* **Publication:** *Communications of the ACM*, Vol. 27, No. 3, pp. 236–239, March 1984
* **DOI:** [10.1145/357994.358023](https://doi.org/10.1145/357994.358023)

---

## 🔬 Theoretical Background & Methodology
* **Course Context:** Gonzalez & Woods (*Digital Image Processing*), Chapter 9: **Morphological Image Processing (Thinning and Skeletons)**
* **Algorithm Summary:** The Zhang-Suen algorithm is a parallel thinning method that removes boundary and corner pixels iteratively while preserving connectivity and endpoints.
  Each iteration is divided into two distinct subiterations:
  1. **First Subiteration:** Targets south-east boundary points and north-west corner points.
  2. **Second Subiteration:** Targets north-west boundary points and south-east corner points.
* **Library Comparison:** Results from the custom implementation are compared against the optimized library function **`skimage.morphology.skeletonize`**

---

## 📂 Repository Structure

```text
├── data/               # Binary shapes, scanned handwriting, and test datasets
├── docs/               # Reference papers and documentation
├── src/                # Jupyter notebooks and Python source codes
├── results/            # Output images, comparison charts, and figures
├── requirements.txt    # Python package dependencies
└── README.md           # Project documentation
