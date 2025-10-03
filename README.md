# F1-DATA602-project


## Topic: Formula 1

Formula 1 (F1) is the world’s leading motorsport, blending advanced technology and elite driver skill in races held globally. Since its debut in 1950, F1 has drawn millions of fans through its dramatic Grand Prix events and technical innovation. The sport features engineering marvels—single-seater cars reaching extraordinary speeds on diverse circuits from Monaco to Silverstone. With over 826 million global followers in 2025, F1 is a prime example of big data and real-time analytics in action. Integrating Formula 1 data into machine learning projects enables powerful insights into strategy, performance, and predictive modeling


## Project: Podium Predictor

The goal of this project is to develop a machine learning model that predicts whether a driver will finish on the podium (in the top 3) in a Formula 1 Grand Prix. By analyzing historical race data, the model aims to identify the key factors that contribute to a successful race outcome.

## Dataset

This project's predictions are built on two complementary data sources to provide both historical depth and modern, high-frequency data:

* **[Formula 1 World Championship (1950-2020)](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020):** A comprehensive historical dataset from **Kaggle**. It contains relational tables on decades of F1 history, making it ideal for training a baseline model on long-term race outcomes. Key files include:
    * `races.csv`
    * `results.csv`
    * `qualifying.csv`
    * `driver_standings.csv`

* **[OpenF1 API](https://openf1.org/):** A modern data source from **OpenF1** providing live telemetry data from recent seasons. This high-frequency data is perfect for advanced feature engineering (e.g., analyzing in-race pace and tire degradation). Key data points include:
    * Car position and speed
    * RPM, gear, and DRS status
    * Lap times and pit stops

By combining the historical breadth of the Kaggle dataset with the real-time depth of the OpenF1 API, the project can build a robust and nuanced prediction model.


## Group Members
1. Ravichandra Parvatham
2. Shreeya Dasa Lakshminath
3. Hemanth Thulasiraman
