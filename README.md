# JPEG-AI-SDR25 Dataset

**Repository:** `dataset-JPEG-AI-SDR`

**Download the dataset:**  
[JPEG-AIC-4-Example-Dataset](https://plenodb.jpeg.org/aic4/JPEG-AIC-4-example-dataset.zip)

## Overview

This dataset contains subjective quality assessment data collected for the JPEG AIC-3 activities. The study is based on *boosted triplet comparisons* (BTC) and *perceptual toggle comparisons* (PTC), and was conducted on Amazon Mechanical Turk (MTurk) from January 4 to January 10, 2024.

For detailed information about the **BTC method**, see the methodology presented in:  
Testolina, Michela, Mohsen Jenadeleh, Shima Mohammadi, Shaolin Su, Joao Ascenso, Touradj Ebrahimi, Jon Sneyers, and Dietmar Saupe. "Fine-grained subjective visual quality assessment for high-fidelity compressed images."  
arXiv: [2410.09501](https://arxiv.org/pdf/2410.09501)

---

## Subjective Data Included Files

- `JPEG_AIC_SDR_BTC_JPEG_AI_responses_2025.02.28_v1.csv`
- `JPEG_AIC_SDR_BTC_JPEG_AI_user_data_2025.02.28_v1.csv`
- `JPEG_AIC_SDR_PTC_JPEG_AI_responses_2025.02.28_v1.csv`
- `JPEG_AIC_SDR_PTC_JPEG_AI_user_data_2025.02.28_v1.csv`

---

## File Descriptions

### `JPEG_AIC_SDR_BTC_JPEG_AI_responses_2025.02.28_v1.csv`

Responses from participants in the BTC (Boosted Triplet Comparison) experiment.

#### Columns

| Column Name       | Type        | Description                                                                                      |
|-------------------|-------------|--------------------------------------------------------------------------------------------------|
| `assignment`      | Categorical | Unique identifier for each assignment.                                                          |
| `worker`          | Numeric     | Anonymized ID of the worker.                                                                    |
| `method`          | Categorical | Method used (BTC).                                                                              |
| `task`            | Numeric     | Task number.                                                                                     |
| `question_id`     | Numeric     | Unique question ID.                                                                             |
| `img_num`         | Numeric     | Source image ID.                                                                                |
| `codec_left`      | Numeric     | Codec used for the left image.                                                                  |
| `codec_pivot`     | Numeric     | Codec used for the pivot (reference) image.                                                     |
| `codec_right`     | Numeric     | Codec used for the right image.                                                                 |
| `dlevel_left`     | Numeric     | Distortion level of the left image.                                                             |
| `dlevel_pivot`    | Numeric     | Distortion level of the pivot image.                                                            |
| `dlevel_right`    | Numeric     | Distortion level of the right image.                                                            |
| `img_left`        | Categorical | Filename of the left image.                                                                     |
| `img_pivot`       | Categorical | Filename of the pivot image.                                                                    |
| `img_right`       | Categorical | Filename of the right image.                                                                    |
| `is_same`         | Logical     | Whether all codecs are the same (0 or 1).                                                       |
| `is_cross`        | Logical     | Whether it's a cross-codec triplet (0 or 1).                                                    |
| `is_bias`         | Logical     | Bias-control triplet (left and right images are the same codec and distortion) (0 or 1).       |
| `is_trap`         | Logical     | Trap question (one image is original, the other heavily distorted) (0 or 1).                   |
| `question_order`  | Numeric     | Order of the question shown to the user.                                                        |
| `response`        | Categorical | Response: `left`, `right`, or `not sure`.                                                       |
| `submission_time` | Datetime    | ISO 8601 formatted submission timestamp.                                                        |
| `response_time`   | Numeric     | Time taken to respond (in seconds).                                                             |
| `reload_count`    | Numeric     | Number of times the task page was reloaded.                                                     |
| `resolution`      | Categorical | Screen resolution of the worker’s device.                                                      |

---

### `JPEG_AIC_SDR_BTC_JPEG_AI_user_data_2025.02.28_v1.csv`

Demographic data for participants in the BTC experiment.

#### Columns

| Column Name       | Type        | Description                                                                                      |
|-------------------|-------------|--------------------------------------------------------------------------------------------------|
| `worker`          | Numeric     | Anonymized worker ID.                                                                            |
| `age`             | Categorical | Age range (e.g., '18–25').                                                                       |
| `gender`          | Categorical | Gender of the participant.                                                                       |
| `time_zone`       | Categorical | Time zone where the task was completed.                                                          |
| `display_size`    | Numeric     | Diagonal size of display in inches.                                                              |
| `tasks`           | Numeric     | List of completed task IDs.                                                                      |
| `assignments`     | String      | List of assignment IDs.                                                                          |
| `completion_time` | Numeric     | List of completion times in seconds.                                                             |
| `ishihara_test1`  | Numeric     | Response to Ishihara color blindness test 1 (ground truth: 2).                                   |
| `ishihara_test2`  | Numeric     | Response to Ishihara color blindness test 2 (ground truth: 16).                                  |

---

### `JPEG_AIC_SDR_PTC_JPEG_AI_responses_2025.02.28_v1.csv`

Responses from participants in the PTC (Perceptual Toggle Comparison) experiment. Format is the same as the BTC responses file, with one additional column:

| Column Name     | Type      | Description                                                    |
|-----------------|-----------|----------------------------------------------------------------|
| `toggle_count`  | Numeric   | Number of toggles between the reference and test images.       |

---

### `JPEG_AIC_SDR_PTC_JPEG_AI_user_data_2025.02.28_v1.csv`

Demographic data for participants in the PTC experiment. Format is the same as the BTC user data file, with one additional column:

| Column Name     | Type      | Description                                                    |
|-----------------|-----------|----------------------------------------------------------------|
| `country`       | String    | Country of residency provided by the participant.              |
---

## Usage Notes

- Use appropriate data parsers to correctly interpret `categorical`, `logical`, and `datetime` columns.
- `submission_time` is provided in ISO 8601 format.

## Contact
First author:mohsen.jenadeleh@uni-konstanz.de

JPEG-AIC chairs:

Dietmar Saupe: dietmar.saupe@uni-konstanz.de

Jon Sneyers: jon@cloudinary.com
