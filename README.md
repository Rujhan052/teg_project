Thermoelectric Generator (TEG) Prediction Project

Overview:

This project explores how thermoelectric generators (TEGs) behave under different conditions, focusing on predicting power output and efficiency using machine learning.

The dataset includes features such as temperature difference across the module (ΔT), electrical load resistance, and Seebeck coefficient. The target variables are power generated (W) and efficiency (%).

Steps in the Project:
1) Data Preparation

     Loaded raw dataset (TEG_with_targets.csv).

     Identified input features:

        ΔT (Temperature Difference, °C)

        Rload (Load Resistance, Ω)

        Seebeck Coefficient (V/K)

    Identified target variables:

        Power Output (W)

        Efficiency (%)

2) Feature Scaling

    Applied MinMaxScaler to scale both features and target variables into a 0–1 range.

    Created a combined dataset (TEG_ml.csv) for model training.

3) Model Training

    Used and compared linear regression and random forest model to predict power and efficiency from the scaled features.

    Split data into training and testing sets.

    Evaluated predictions against actual values using standard regression metrics (e.g., R², MSE).

4) Observations

    Power and efficiency both increased with ΔT up to an optimal point, then leveled off.

    Load resistance strongly influenced output performance.

    The trained model could reasonably capture these relationships.

5) Results

    Model was able to predict both targets with fair accuracy and a R2 score of 99%.

    Example predicted vs actual plots showed good alignment, indicating the model learned meaningful patterns.


