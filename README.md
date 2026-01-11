# Manual Annotation of Red-Winged Blackbird Vocalizations Using Raven Lite

## Overview

This repository documents a bioacoustic annotation workflow for manually labeling red‑winged blackbird (Agelaius phoeniceus) song vocalizations. The project demonstrates how to create consistent, high‑quality annotations using Raven Lite and how to summarize temporal and spectral characteristics of annotated songs using Python. 

The focus is intentionally narrow: only song vocalizations from a single species, recorded within the United States, were included. Non‑song calls and background sounds were excluded to maintain consistency and reduce acoustic variability unrelated to the target behavior.

## Dataset Source

All recordings were sourced from xeno‑canto.org, a community‑curated repository of global bird sound recordings.

## Annotation Workflow

1. Selected red‑winged blackbird recordings from xeno‑canto.

2. Annotated each recording manually in Raven Lite, identifying complete song vocalizations.

3. Exported annotation tables for each recording (required due to varying recording parameters such as sample rate and channel count).

4. Combined all annotation tables into a unified dataset.

5. Computed derived variables from annotation bounds, including:

	* Song duration (seconds)

	* Frequency range (kHz)

6. Generated summary statistics and visualizations to explore temporal and spectral patterns.

## Annotation Protocol

Song units were annotated by drawing time–frequency bounding boxes around complete vocalizations. Only songs were included; calls and other non‑song vocalizations were excluded. When recordings contained multiple song bouts, each bout was annotated as a separate selection.

## Tools and Technologies

* Raven Lite
* Jupyter Notebook
* Python
* NumPy
* Pandas
* Matplotlib

## Raven Lite Configuration

Spectrograms were generated using Raven Lite’s default settings:

* Window type: Hann
* Window size: 512 samples
* Overlap: 50%
* DFT size: automatically determined by Raven Lite

These defaults were used to maintain consistency across all recordings and to reflect typical Raven Lite usage in entry-level annotation workflows.

## Summary of Observations

* Most annotated songs had durations between 1.1 and 1.3 seconds, with fewer very short or long selections.

* Songs generally occupied a consistent frequency band, though some variation was observed.

* Variation in frequency range may reflect recording conditions and natural vocal variability.	

* Some recordings were labeled as originating from different subspecies or regions, though subspecies-level differences were not analyzed in this project.

## Limitations

* Raven Lite’s fixed spectrogram settings limit fine‑tuning of visualization parameters.

* While adequate for manual annotation, these settings may differ from those used in automated detection workflows.

* Subspecies‑level variation was not examined, though recordings included individuals labeled from multiple regions.

## Repository Structure

- Data/Annotations_raw/ — CSV files exported from Raven Lite
- Data/Annotations_combined/ — combined master of CSV files, cleaned master file
- Figures/ — Selected spectrogram screenshots and generated plots
- Notebooks/ — Jupyter notebook for data aggregation, analysis, and visualization



