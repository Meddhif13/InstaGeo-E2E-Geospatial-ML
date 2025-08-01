# GeoAI Hackathon Summary

This repository contains material from the 2024 GeoAI Hackathon, an event focused on applying geospatial machine learning techniques to environmental challenges. Our team used the **InstaGeo** framework to tackle the hackathon task of predicting locust breeding grounds from multi-spectral satellite imagery.

## Challenge Overview
The hackathon provided a labelled dataset of locust breeding ground observations together with aligned Harmonized Landsat and Sentinel-2 (HLS) image chips. Participants were asked to build an automated approach for detecting potential breeding locations using the satellite imagery.

## Our Approach
The solution implemented in [`notebook4b7ce1b379.ipynb`](notebook4b7ce1b379.ipynb) leverages the functionality of the InstaGeo package:

1. **Data preparation** – The notebook first creates CSV files mapping HLS chips to their corresponding segmentation labels and splits the dataset into training and validation sets.
2. **Model configuration** – We fine-tuned a Prithvi-based segmentation model using the configuration in `instageo/model/configs/locust.yaml`, adjusting mean and standard deviation values to match the dataset.
3. **Training** – The model is trained for 10 epochs on the locust dataset using the InstaGeo training loop.
4. **Evaluation and inference** – After training, the notebook performs evaluation on a validation split and generates predictions for the test chips. Those predictions are aggregated back to point observations to create the submission file.

## Results
This approach produced competitive results in the hackathon leaderboard. The full workflow can be reproduced by executing the notebook on Kaggle with the `geo-ai-hack` dataset mounted in the input directory.

