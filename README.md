PL Neural Data Analysis Pipeline

This repository provides a complete analysis pipeline for processing and analyzing neural calcium imaging data from the prelimbic cortex (PL) during behavioral experiments. The workflow includes data cleaning, functional ensemble classification, within- and across-session activity quantification, overlap analysis (observed vs. chance-level), and visualization.

1. System Requirements

1.1 Operating Systems 

Tested on: macOS 10 (Catalina), Windows 11. (Any platform that supports Python 3.x and Jupyter Notebook)

1.2 Software Dependencies

All code is written in Python 3.10 and requires the following packages (with version numbers used in our tests):
Package	Version:
numpy	1.26.4,
pandas	1.5.3,
matplotlib	3.5.3,
seaborn	0.13.2,
scipy	1.15.3,
scikit-learn	1.5.0,
jupyter	5.5.0,
openpyxl	3.1.2.

1.3 Hardware Requirements

A standard computer with ≥ 32 GB RAM, ≥ 1T SSD hard drive, and ≥ 5 cores is sufficient for all analyses. For large datasets, 64 GB RAM is recommended.

2. Installation Guide

Step 1: Install Python and Jupyter
If you do not already have Python, we recommend installing the Anaconda Distribution which includes Python, Jupyter Notebook, and most required packages.

Step 2: Install required packages
Open a terminal (or Anaconda Prompt) and run: "pip install numpy pandas matplotlib seaborn scipy scikit-learn jupyter openpyxl".

Step 3: Download the code
Clone this repository or download the provided file to your local machine.

Typical install time
On a normal desktop computer with a broadband internet connection, the entire installation (including dependencies) takes less than 5 minutes.

3. Demo

3.1 Demo data

A small simulated dataset is included in the demo_data (zip file). These files mimic the structure of real calcium traces and behavioral event logs.

3.2 Instructions to Run on Demo Data

(1) Launch Jupyter Notebook from the terminal.
(2) Open any of the analysis notebooks (e.g., 2-ONOFF_classification_SocB_Any_session.ipynb).
(3) Change the file paths at the top of the notebook to point to the demo data folder.
(4) Run all cells sequentially (Cell → Run All)

3.3 Expected output

For each notebook, the expected outputs are:

Notebook 1:	    Cleaned trace CSV (no "rejected" columns) saved in outputs.

Notebook 2:	    Ensemble classification labels (ON/OFF) per neuron, saved as XLSX.

Notebook 3–4:	    Activity metrics (transient rate, amplitude) per event type, saved as CSV.

Notebook 5–6:	    Overlap proportions (observed and chance-level), saved as CSV.

Notebook 7:	    Behavioral timeline plot (.png) saved in figures.

Notebook 8:	    ROI spatial distribution plot (.png) saved in figures.

Notebook 9:	    Heatmap and averaged trace (.png) saved in figures.

All output files are written to the outputs and figures subdirectories.

3.4 Expected Run Time for Demo

On a computer (Intel i7, 64 GB RAM), running the entire demo pipeline from start to finish takes approximately 60 minutes (most notebooks complete in under 1 minute each; notebook 2 may take about 30-50 minutes to classify neurons; notebook 8 and 9 may take 1-2 minutes for plot generation).

4. Instructions for Use 

4.1 Data Preparation

Calcium trace files: CSV files where each column is a neuron’s ΔF/F trace over time (one row per time point). Columns labelled "rejected" are automatically removed.
Behavioral event files: Excel files (.xlsx) with columns: Event (string), From Second (float), To Second (float).

4.2 Running the Pipeline on Data

a. Preprocess trace files using 1-convert-SocB.ipynb to simply specify the input folder and output folder.

b. Classify neurons into ON/OFF ensembles for each session using 2-ONOFF_classification_SocB_Any _session.ipynb. Set the session ID and the target behavioral event (e.g., 'cs' or 'sniff').

c. Compute transient rates and amplitudes within‑session (notebook 3) and across‑session (notebook 4) by providing the ensemble label and the session(s) of interest.

d. Analyze overlaps within‑session (notebook 5) and across‑sessions (notebook 6), the scripts will automatically compute both observed and chance‑level overlaps.

e. Generate visualizations using notebooks 7–9:
Notebook 7: plots behavioral timelines.
Notebook 8: plots maps neuron spatial distributions.
Notebook 9: produces heatmaps and averaged population traces.

All scripts contain inline comments and markdown cells explaining each step. Parameter settings (paths, event types, session IDs) are concentrated at one part of each notebook for easy modification.

6. License

This project is distributed under the MIT License (an OSI-approved license). See the LICENSE file in the repository for full terms.

7. Code Description in Manuscript

A detailed pseudocode description of the core classification and overlap algorithms is provided in the Methods section of the manuscript (see subsection " Analysis of single cell responses during SBF test").

8. Contact & Support

For questions or issues, please contact the corresponding author at clamslowly@163.com.

