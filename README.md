# DelivTimeAI

The DelivTimeAI project leverages Conformalized Quantile Regression to forecast Food Delivery Time with Uncertainty Quantification. In today's world where e-commerce is ubiquitous and most goods are shipped with an ETA estimator, uncertainty quantification becomes crucial for accurate delivery time predictions.

## Sections

The project is divided into three sections:

### 1) EDA

In this section, I performed exploratory data analysis on the dataset. The dataset can be found in the [EDA.ipynb](EDA.ipynb) notebook. The notebook contains a comprehensive analysis of the dataset, including key insights such as the number of delivery persons, distribution and average age of delivery persons, most popular type of order, most popular type of delivery vehicle, average distance per order, average time taken per order, and factors affecting delivery time the most.

### 2) Regression using a Neural Network in PyTorch

In the second section, I implemented regression using a neural network in PyTorch. The prediction models can be found in the [Prediction_Model.ipynb](Prediction_Model.ipynb) notebook. After training the model for 1000 epochs, I achieved a low root mean squared error (RMSE) of 8.2. However, the results were not satisfactory as they did not provide enough useful information for decision-making purposes. Below is the graph of the initial model results:

![Initial Model Results](initial_model.png)

### 3) Conformalized Quantile Regression for Prediction Intervals

In this section, I utilized Conformalized Quantile Regression (CQR) to create prediction intervals for delivery time. CQR provides an intuitive way of uncertainty quantification by outputting a lower bound and an upper bound within which the true value is likely to lie. The length of the prediction interval is shorter for more certain predictions and larger for less certain ones.

The CQR approach offers two essential components:

- Coverage guarantee from a prespecified required coverage rate, which can be used as a hyperparameter.
- Dynamic prediction intervals that are as short as possible.

I implemented CQR using the LightGBM and MAPIE libraries. The results obtained include a coverage rate of 0.9, indicating that 90% of the true values lie within the predicted intervals. The prediction intervals are dynamic and as short as possible. The results are shown in the image below:

![CQR Results](cqr_result.png)

## Future Work

Future work on this project can focus on further optimizing the model to achieve even higher coverage rates and shorter prediction intervals. Additionally, deploying the model on an e-commerce website can provide valuable insights and accurate delivery time estimates to customers.

Feel free to explore the code and experiment with different approaches to enhance the accuracy and efficiency of the DelivTimeAI model.
