# TimesFM Geomagnetic Forecasting

Evaluating zero-shot forecasting, in-context learning, and Low-Rank Adaptation (LoRA) of TimesFM 2.5 on geomagnetic time-series data.

## Overview

This project investigates the transferability of pretrained time-series foundation models to geomagnetic forecasting. Specifically, it evaluates **Google Research's TimesFM 2.5**, a pretrained time-series forecasting model, on geomagnetic indices such as Dst, AE, and Kp.

The primary objective is to determine how effectively TimesFM generalizes to specialized geophysical time series without task-specific training and whether parameter-efficient fine-tuning improves forecasting accuracy.

This project is being developed as part of **DS 733: Deep Unsupervised Learning** at the New Jersey Institute of Technology (NJIT).

## Research Objectives

The project investigates three approaches:

1. **Zero-Shot Forecasting:** Evaluate pretrained TimesFM 2.5 directly on geomagnetic time series without updating model parameters.
2. **In-Context Learning:** Investigate whether alternative historical context configurations improve forecasting performance without parameter updates.
3. **LoRA Fine-Tuning:** Adapt TimesFM 2.5 to geomagnetic data using low-rank parameter updates and compare performance against zero-shot predictions.

A persistence forecasting baseline will also be implemented to provide a reference for evaluating model performance.

## Datasets

The project focuses on geomagnetic indices describing different aspects of Earth's magnetic environment.

| Index   | Description                                                                  | Typical Resolution |
| ------- | ---------------------------------------------------------------------------- | ------------------ |
| **Dst** | Disturbance Storm Time index, measuring large-scale geomagnetic disturbances | Hourly             |
| **AE**  | Auroral Electrojet index, describing auroral-zone geomagnetic activity       | 1 minute           |
| **Kp**  | Planetary geomagnetic index, characterizing global geomagnetic activity      | 3 hours            |

### Data Sources

* **World Data Center for Geomagnetism, Kyoto:** Historical Dst and AE indices.
* **Geomagnetic observatory archives:** Additional geomagnetic index datasets.

The initial dataset consists of historical hourly Dst measurements obtained from the World Data Center for Geomagnetism, Kyoto.

## Methodology

### Data Preparation

* Acquire historical geomagnetic index measurements.
* Inspect temporal coverage, missing values, and data quality.
* Construct chronological training, validation, and testing partitions.
* Generate historical context windows and forecasting targets.

### Forecasting Experiments

All approaches will be evaluated using consistent forecasting configurations where applicable.

**Zero-Shot Evaluation**

Use pretrained TimesFM 2.5 to forecast future geomagnetic index values directly from historical observations.

**In-Context Learning**

Investigate how different historical context configurations affect forecasting performance without modifying pretrained model parameters.

**LoRA Adaptation**

Apply parameter-efficient fine-tuning to TimesFM 2.5 using geomagnetic time-series data.

### Evaluation

Planned evaluation metrics include:

* **Mean Absolute Error (MAE)**
* **Mean Absolute Scaled Error (MASE)**

Experiments will compare forecasting accuracy across different adaptation approaches, geomagnetic indices, and forecasting horizons.

## Project Status

**Status: Initial Development**

* [x] Research proposal approved
* [x] Identify initial Dst data source
* [x] Acquire historical Dst measurements
* [ ] Inspect and preprocess Dst dataset
* [ ] Establish persistence baseline
* [ ] Implement TimesFM 2.5 zero-shot evaluation
* [ ] Investigate in-context learning approaches
* [ ] Implement LoRA adaptation
* [ ] Evaluate AE and Kp forecasting
* [ ] Compare experimental results

## References

* [TimesFM — Google Research](https://github.com/google-research/timesfm)
* [TimesFM 2.5 — Hugging Face](https://huggingface.co/google/timesfm-2.5-200m-pytorch)
* [World Data Center for Geomagnetism, Kyoto](https://wdc.kugi.kyoto-u.ac.jp/)
* [Kyoto Dst Index Portal](https://wdc.kugi.kyoto-u.ac.jp/dstdir/index.html)

## License

License to be determined.