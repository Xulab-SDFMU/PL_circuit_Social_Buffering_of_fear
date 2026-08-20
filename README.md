PL Neural Data Analysis Pipeline
This repository contains a comprehensive analysis pipeline for processing and analyzing neural calcium imaging data from the prelimbic cortex (PL) during SBF behavioral experiments. The workflow covers data preprocessing, neural ensemble classification, activity quantification, overlap analysis, and visualization.

Code Overview
1. Data Preprocessing
1-convert-SocB.ipynb
Preprocesses raw neural signal trace files by removing columns labeled "rejected" to clean the dataset for subsequent analysis.

2. Neural Ensemble Classification
2-ONOFF_classification_SocB_Any_session.ipynb
Classifies PL neurons into functional ensembles (e.g., "ON") based on the similarity between calcium transient vectors and behavioral event vectors within a given session.

3. Within-Session Activity Quantification
3-TransientRate_Amplitude_SocB_ON_neurons_within_session.ipynb
Calculates transient rate and amplitude for a specific ON neural ensemble (identified in one session) during behavioral events occurring in the same session.

4. Across-Session Activity Quantification
4-TransientRate_Amplitude_SocB_ON_neurons_across_session.ipynb
Calculates transient rate and amplitude for a specific ON neural ensemble (identified in one session) during behavioral events across all testing sessions, enabling longitudinal comparison.

5. Within-Session Ensemble Overlap
5-Neuron_overlap_proportion_Allsessions.ipynb
Computes: (1) the proportion of each neural ensemble within a session.
     (2) the observed overlap between two neural ensembles in the same session.
                  (3) the chance-level overlap predicted by random distribution.

6. Across-Session Ensemble Overlap
6-Neuron_overlap_Across_sessions-output improved.ipynb
Computes: (1) The observed overlap between two neural ensembles from different sessions.
     (2) The corresponding chance-level overlap for cross-session comparisons.

7. Behavioral Timeline Visualization
7-PLOT-behavior event.ipynb
Generates color-coded timeline plots of behavioral events (e.g., freezing, CS presentation, sniffing) across experimental sessions for visual inspection of temporal patterns.

8. ROI-Based Neuron Distribution Plotting
8-PLOT_ON_neuorn_overlap_Across_sessions.ipynb
Visualizes the spatial distribution of neurons within the region of interest (ROI), with neural ensembles from the same or different sessions labeled in distinct colors.

9. Activity Heatmap and Averaged Traces
9-PLOT_ON_neuorn_heatmap_and_Trace.ipynb
Plots the heatmaps of neuronal activity aligned to the onset of a specific behavioral event, and the averaged population traces to visualize temporal dynamics across the ensemble.

Requirements
•	Python 3.x
•	Jupyter Notebook
•	Standard scientific libraries: numpy, pandas, matplotlib, seaborn, scipy, etc.


