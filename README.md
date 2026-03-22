# deep-learning-medical-imaging
A curated collection of papers, code resources, and notes on Deep Learning for Medical Image Analysis.

Deep Learning for Medical Imaging

A structured, evolving knowledge base and code repository for cutting-edge research in Deep Learning applied to Medical Image Analysis. This repository organizes papers, implementations, datasets, and fundamental concepts to accelerate learning and research in this specialized field.

📁 Repository Architecture Overview

The repository is organized to separate conceptual knowledge, practical code, and essential resources, following a clear progression from fundamentals to advanced applications.

deep-learning-medical-imaging/
├── 01-Papers-Notes/                # 【Core】 Paper notes, categorized by task
├── 02-Code-Implementations/       # 【Practical】 Runnable code/reproduction attempts
├── 03-Datasets/                   # 【Essential】 Guides for medical datasets
├── 04-Fundamentals/               # 【Foundation】 Prerequisite knowledge
├── 05-Challenges-Competitions/    # 【Frontier】 Track of competitions
└── Resources/                     # 【Network】 Curated resource lists


🧭 Navigation Guide

1. 01-Papers-Notes/ - The Core Literature

Contains detailed notes on seminal and state-of-the-art papers, categorized by primary task. Each note follows a structured template to ensure consistency and depth.

•   01-Segmentation/: The largest sub-field. Notes on foundational (U-Net, nnU-Net) and advanced (Transformer-based) methods.

•   02-Classification/: Papers on disease diagnosis and classification from images.

•   03-Detection-Localization/: Focus on lesion, organ, or landmark detection.

•   04-Registration/: Aligning different images or modalities.

•   05-Reconstruction/: Techniques for generating images from sensor data (e.g., MRI/CT reconstruction).

•   06-Generative/: Image synthesis, augmentation, and domain translation (e.g., GANs, Diffusion Models).

2. 02-Code-Implementations/ - From Theory to Practice

A space for executable code, scripts, and reproduction attempts. The goal is to bridge the gap between paper descriptions and working models.

•   Each sub-folder (e.g., nnUNet/) typically contains:

    ◦   A README.md with setup instructions and specific notes.

    ◦   Training/evaluation/inference scripts.

    ◦   Configuration files and environment specs.

3. 03-Datasets/ - The Data Landscape

Medical AI is data-defined. This section provides concise guides for major public datasets.

•   Overview.md: A comparative table of datasets by modality, task, and size.

•   Sub-folders (CT/, X-Ray-MRI/): Detailed notes per dataset covering access, structure, preprocessing, and usage tips.

4. 04-Fundamentals/ - Foundational Knowledge

Essential reading before diving into papers. Explains concepts specific to medical image analysis.

•   Preprocessing.md: Standard pipelines (resampling, windowing, normalization).

•   Evaluation.md: Medical-specific metrics (Dice, HD95, Sensitivity, Specificity).

•   Clinical-Concepts.md: Brief explanations of relevant clinical terms and context.

5. 05-Challenges-Competitions/ - The Cutting Edge

Tracks top medical imaging challenges (e.g., from MICCAI, Kaggle) and their winning solutions. Great for understanding state-of-the-art and practical problem-solving.

6. Resources/ - Extended Ecosystem

A curated, community-style list of external resources: tutorials, blogs, courses, software tools, and prominent research labs.

🚀 Getting Started

For Beginners:
1.  Start with 04-Fundamentals/ to understand preprocessing and evaluation.
2.  Read the classic 2020-UNet++.md and 2022-nnUNet.md in 01-Papers-Notes/01-Segmentation/.
3.  Browse 03-Datasets/Overview.md to see what data is available.

For Practitioners:
1.  Check 02-Code-Implementations/ for runnable examples.
2.  Explore 05-Challenges-Competitions/ for the most recent advances.

For Researchers:
1.  The 01-Papers-Notes/ is organized to help you quickly find literature by task.
2.  Use the Resources/awesome-medical-imaging.md to find tools and further reading.

📝 Contributing

This is a personal learning repository, but suggestions are welcome. If you spot an error or have a great paper to suggest, please open an Issue.

📄 License

The content of this repository (notes, summaries) is shared under a http://creativecommons.org/licenses/by/4.0/. Code snippets are under the https://opensource.org/licenses/MIT. Always check the respective licenses for papers, datasets, and external code referenced herein.

This repository is maintained as part of a personal journey to deeply understand and contribute to the field of medical image analysis.
