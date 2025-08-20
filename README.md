This code is divided into two stages: pre-training and fine-tuning, based on the graph structure and multi-level attention neurological and psychiatric disorders assigned diagnosis model, the current public code is the core code part, and will be encapsulated into a system for disclosure in the future.

The results of the division of the brain network are shown in ROI.xlsx,1-8 represent DefaultMode, SensoriMotor, Visual, Salience, DorsalAttention, FrontoParietal, Language, and Cerebellar brain networks, respectively

The reported results and comparisons are based on the best-performing configurations of each model，ensure that the sample size of different categories selected for each experiment is balanced.
Specifically, for the submatrix selection process, the value of k was set to 32, following prior empirical studies in similar settings.
For the K-best feature selection algorithm, K was chosen within the range of 75 to 225 based on established practices in previous literature.
All baseline methods and our proposed model were evaluated using the same extracted subgraphs to ensure a fair and consistent comparison.

Important: The results in Figure 5 are from a single fold, intended solely to demonstrate the variation across parameter values.


Contribution summary:This work proposes a graph structure modeling approach inspired by neural transmission processes driven by Functional Connectivity. To better capture the dynamics of neural interactions, intermediate nodes are introduced, enabling edge updates through a learnable indirect correlation coefficient. Assuming a consistent quantity of neural signal is transmitted between nodes, parameter constraints ensure that each update is performed under uniform transmission conditions. Updates are applied only when the original connections are enhanced after passing through intermediate nodes, aligning the model more closely with real neural pathways while avoiding the introduction of redundant information. It reflects the process of continuously learning to find the optimal transmission path when brain signals are transmitted. Update the structural information stored in the vertices based on changes in brain results due to new topological features from edge adjustments, combining them to better represent the brain structure. The Multi-level attention mechanism combined with pathological mechanism comprehensively updates hyperparameters in the graph from three levels: individual, regional, and global. Combined with graph structure modeling, it obtains more interpretable results and weights the features reasonably.


Description of Multimodal Data
﻿    The multimodal data used in this study are sourced from the Alzheimer’s Disease Neuroimaging Initiative (ADNI) project and include both cognitive assessment data and genomic biomarker data. ADNI employed modern psychometric methods to evaluate variables such as education, memory, executive function, language, and visuospatial ability. All preprocessing steps for both the cognitive and biomarker data were performed by the ADNI research team.
  Processing of Neuropsychological Assessment Data:
    For the neuropsychological assessment data, various cognitive test items—including the Mini-Mental State Examination (MMSE)—were categorized into four cognitive domains: memory, executive function, language, and visuospatial ability. A confirmatory factor analysis (CFA) model was applied to jointly calibrate item parameters across all assessment items. Using these calibrated parameters, factor scores and their corresponding standard deviations were estimated for each domain and each participant. These factor scores, provided by ADNI, were used as the input data for this modality. The missing rate for this modality was 9.3%.
  Processing of Biomarker and Genomic Data:
    For the biomarker and genomic data, ADNI conducted all preprocessing procedures. Duplicate data points were removed through co-calibration. Log10-transformed biomarker values were used to detect outliers, which were defined as values beyond Q3 + 1.5 × IQR or below Q1 − 1.5 × IQR (with IQR denoting the interquartile range, and Q1 and Q3 representing the first and third quartiles, respectively). After outlier exclusion, Z-scores were calculated for each fluid biomarker using the scaling function in R, based on the remaining valid data. These standardized Z-scores were used as input for this modality, which had a missing rate of 4.9%.











