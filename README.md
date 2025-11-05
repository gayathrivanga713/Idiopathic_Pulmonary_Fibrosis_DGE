Idiopathic Pulmonary Fibrosis (IPF) Differential Gene Expression Analysis:

This project focuses on identifying **differentially expressed genes (DEGs)** in **Idiopathic Pulmonary Fibrosis (IPF)** compared to **healthy controls** using RNA-Seq data from **GSE150910**.  
The analysis was performed entirely in **Python**, without using DESeq2 or R-based tools.

What is Idiopathic Pulmonary Fibrosis?

- **Idiopathic** → means there is no known cause (why this scarring happens).  
- **Pulmonary** → means lung.  
- **Fibrosis** → means scarring.  
- It is a **chronic lung disease** where scar tissue gradually forms in the lungs without a known cause.  
- This scarring makes the lungs stiff and less able to expand, leading to breathing difficulties and reduced oxygen transfer.

**Key points:**
- Progressive disease (gets worse over time).  
- Main symptoms: *Shortness of breath, dry cough, fatigue.*  
- There is no cure, but medications can slow progression.

Dataset Information

- **Dataset ID:** [GSE150910](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE150910)  
- **Source:** NCBI Gene Expression Omnibus (GEO)  
- The dataset includes **2 diseased groups (IPF & CHP)** and **1 healthy control** group.

My Analysis
- I filtered out **Chronic Hypersensitivity Pneumonitis (CHP)** samples.  
- Focused only on **IPF (Diseased)** vs **Control (Healthy)** samples.  
- Downloaded the **gene-level count CSV file** for downstream analysis to determine how genes are differentially expressed in both conditions. Ran a **Python script (`DEG_G.py`)** to identify differentially expressed genes (DEGs).  
- The script performs:
  - **CPM normalization**
  - **Kolmogorov–Smirnov test (KS-test)**  
  - **Bonferroni correction and log₂ fold change**
  - Generates **heatmaps and plots** for significant DEGs.

Results Summary
- Identified **upregulated and downregulated genes** in IPF lungs.  
- Example: *POSTN* gene was **highly upregulated** in IPF samples — a known fibrosis marker.  
- Output includes:
  - `upregulated_DEGs.csv`
  - `downregulated_DEGs.csv`
  - `heatmap.pdf`
  - Expression plots for selected genes.

Tools Used
`Python`, `NumPy`, `SciPy`, `Matplotlib`, `Seaborn`


