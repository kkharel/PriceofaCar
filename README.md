# What drives the price of a car?

Link to Notebook: https://github.com/kkharel/PriceofaCar/blob/main/notebook.ipynb

## Objective:

The goal of this analysis is to identify and evaluate the most important features that influence the pricing of used cars, utilizing three machine learning models: Random Forest, Gradient Boosting, and XGBoost. This report summarizes the feature importances obtained from these models and provides insights into their relevance for predicting used car prices. The findings are intended to help used car dealership for better business decision-making and price predictions.

## Overview of Feature Importances and final model:

We assessed feature importances across three models to determine how different attributes influence the prediction of used car prices. The following table summarizes the feature importances for each model, along with the median importance calculated across all models.

| Feature                  | Random Forest | Gradient Boosting | XGBoost  | Median Importance |
|--------------------------|--------------|-------------------|----------|-------------------|
| year                     | 0.424268     | 0.400034          | 0.133780 | 0.400034          |
| odometer                 | 0.148870     | 0.156013          | 0.046731 | 0.148870          |
| drive_fwd                | 0.100361     | 0.095227          | 0.159827 | 0.100361          |
| model                    | 0.085682     | 0.079305          | 0.025742 | 0.079305          |
| fuel_gas                 | 0.043549     | 0.043244          | 0.069952 | 0.043549          |
| cylinders_4 cylinders    | 0.017583     | 0.037201          | 0.100442 | 0.037201          |
| manufacturer             | 0.036564     | 0.048429          | 0.022993 | 0.036564          |
| cylinders_8 cylinders    | 0.033803     | 0.030402          | 0.071276 | 0.033803          |
| type                     | 0.030796     | 0.042194          | 0.027009 | 0.030796          |
| drive_unknown            | 0.012409     | 0.015373          | 0.024122 | 0.015373          |
| transmission_other       | 0.015204     | 0.010392          | 0.028489 | 0.015204          |
| cylinders_6 cylinders    | 0.008977     | 0.006989          | 0.020865 | 0.008977          |
| condition                | 0.006417     | 0.006970          | 0.010940 | 0.006970          |
| title_status_rebuilt     | 0.003794     | 0.004705          | 0.033640 | 0.004705          |
| paint_color              | 0.006327     | 0.002105          | 0.004592 | 0.004592          |
| state                    | 0.006339     | 0.004506          | 0.004564 | 0.004564          |
| fuel_hybrid              | 0.003792     | 0.003896          | 0.052722 | 0.003896          |
| drive_rwd                | 0.003593     | 0.003373          | 0.015805 | 0.003593          |


### Final Model Metrics

| Metric                         | Value              |
|--------------------------------|--------------------|
| **Optimal alpha for Ridge**     | 0.1                |
| **Stacking Model - Mean CV R²** | 0.9284 ± 0.0013    |
| **Train MSE**                   | 0.0457             |
| **Train RMSE**                  | 0.2138             |
| **Train R²**                    | 0.9543             |
| **Test MSE**                    | 0.0681             |
| **Test RMSE**                   | 0.2609             |
| **Test R²**                     | 0.9321             |


## Key Insights from the model:

### Top Features:

Year: The feature year stands out as the most important predictor of used car prices across all models, with a median importance of 0.400. This is consistent with common industry knowledge that the age of a car is a key factor in its price, as older cars tend to be valued lower.

Odometer: The odometer reading, which indicates the number of miles driven, also ranks high in importance (median importance of 0.148), highlighting its strong impact on pricing. Cars with lower mileage are typically priced higher.

Drive Type (FWD): The drive_fwd feature, indicating whether the car is front-wheel drive, has a median importance of 0.100. This reflects the significance of drive type in determining car value, as some drive types may be more desirable in certain markets.

### Moderately Important Features:

Model: The model feature holds moderate importance, with a median value of 0.079. This is likely reflective of the specific model of the car, with more popular or luxury models commanding higher prices.

Fuel Type (Gas): The fuel_gas feature, with a median importance of 0.043, is also moderately important. This suggests that fuel type does influence pricing, although to a lesser extent than year or odometer.

Cylinders: The cylinders features (e.g., cylinders_4 cylinders, cylinders_8 cylinders) show varying levels of importance, with cylinders_4 cylinders being more impactful than the others. Engine size and configuration typically play a role in the car's performance and fuel efficiency, influencing price.

### Low-Impact Features:

Condition: Features like condition (0.006970 median importance) and title_status_rebuilt (0.004705 median importance) have lower importance in predicting the price. Although condition and title status could have a significant impact on the pricing in specific contexts, their overall influence seems less pronounced when compared to factors like the year or odometer reading.

Paint Color and State: These features (paint_color, state) show very low importance, indicating that while they might matter in specific scenarios, they have minimal impact on the overall price prediction.


## Implications for Business:

### Model Refinement:

Based on the feature importances, it’s evident that certain variables like year and odometer should be prioritized when building or refining the pricing model. This suggests that we should focus on improving data collection and ensuring accuracy in these areas.Features with low importance, such as state and paint_color, could be reconsidered for exclusion in future iterations of the model to reduce complexity and improve efficiency.

## Business Strategy:

The high importance of the year and odometer features suggests that any efforts to improve used car valuation should prioritize these attributes. Ensuring that vehicles with lower mileage and newer models are more prominently featured could align with market expectations for higher pricing. Furthermore, understanding the impact of drive type (e.g., front-wheel drive) can guide inventory decisions. Cars with specific drive types may be in higher demand, depending on geographic or market conditions.

## Next Steps:

The results of this analysis suggest that the model is largely well-tuned but could benefit from further refinement. We recommend revisiting the model by either adding more data or fine-tuning hyperparameters to optimize predictions further or using separate model for each segment based on region, model, etc. We also recommend implementing a system for regularly updating the model with new data, ensuring it stays relevant and accurately reflects market trends. Additionally, incorporating external variables such as macroeconomic indicators, local demand shifts, and competitor pricing could further enhance the model’s ability to predict prices. By integrating this predictive model into operations, dealers can gain a strategic edge, improving pricing accuracy and optimizing their inventory for greater profitability. A deeper exploration of lower-impact features could yield additional insights. For instance, examining the condition of the vehicle and its title status may offer greater significance in niche segments of the market, where these factors could vary in importance.

## Conclusion:

The analysis has provided valuable insights into the factors that most influence used car prices. By refining the focus on high-importance features such as year, odometer, and drive type, and considering potential adjustments to lower-importance features, we can optimize the model and offer more accurate predictions for the pricing of used cars. Further model tuning and business strategies can be adjusted based on these findings to drive better decision-making and pricing accuracy.
