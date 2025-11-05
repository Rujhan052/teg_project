Thermoelectric Generator (TEG) Prediction Project

Overview:

This project evaluates machine learning models for predicting the performance of a Thermoelectric Generator (TEG). The objective is to identify the most accurate model for predicting TEG power output and efficiency based on its physical operating conditions.

The dataset includes features such as temperature difference across the module (ΔT), electrical load resistance, and Seebeck coefficient. The target variables are power generated (W) and efficiency (%).

1) Data Preparation
A synthetic dataset of 5,000 samples was generated using NumPy and Pandas. This approach provided a controlled environment to test model performance on data with known non-linear relationships (derived from physics formulas, e.g., $P = V^2 / R$). 

 2) Loaded raw dataset (TEG_with_targets.csv).

     Identified input features:

        ΔT (Temperature Difference, °C)

        Rload (Load Resistance, Ω)

        Seebeck Coefficient (V/K)

    Identified target variables:

        Power Output (W)

        Efficiency (%)

3) Feature Scaling

    Applied MinMaxScaler to scale both features and target variables into a 0–1 range.

    Created a combined dataset (TEG_ml.csv) for model training.

4) Model Training

    Five different regression models were trained and evaluated.

    Performance was measured using the R² (Coefficient of Determination) score and Mean Squared Error (MSE) on the test set.

          Model	R² Score (Higher is better)    	MSE (Lower is better)
   
          XGBoost	~0.996     	~0.000035
   
          Random Forest	~0.992	~0.000075
   
          Decision Tree	~0.985	~0.000140
   
          K-Nearest Neighbors	~0.973	~0.000256
   
          Linear Regression	~0.519	~0.004500

6) Observations

   Impact of Non-Linearity: The Linear Regression model performed poorly, with an R² score of ~0.519. This was expected, as     the model cannot capture the non-linear relationships inherent in the data's physics-based formulas.

   Effectiveness of Non-Linear Models: All other models, which can handle non-linear structures (Decision Tree, KNN, Random     Forest, XGBoost), performed very well, achieving R² scores above 97%.

   Benefit of Ensemble Methods: The Random Forest (R² ~0.992) outperformed the single Decision Tree (R² ~0.985),                demonstrating the stability and accuracy gains from the "bagging" technique.

   Superior Performance of Boosting: The XGBoost model (R² ~0.996) yielded the best performance. This indicates that the        "boosting" technique (sequential learning from errors) was the most effective method for this specific dataset.

7) Conclusion

    This project successfully demonstrated the importance of model selection for non-linear regression problems. The results     clearly show that simple linear models are inadequate for this task. Ensemble and boosting algorithms provided far           superior performance, with XGBoost emerging as the most accurate model, achieving an R² score of 0.996 on the test data.

