# <b>Efficiency-Solutions-for-Heavy-Industry</b>
Prepare a prototype of a machine learning model for a company that develops effective solutions for heavy industry.
The model should predict the amount of gold extracted from the gold ore. You have data on extraction and purification.
The model will help to optimize production and eliminate unprofitable parameters.
## Technological Process
Mined ore undergoes primary processing to get the ore mixture or rougher feed, which is the raw material for flotation (also known as the rougher process). After flotation, the material is sent to two-stage purification.
### Flotation
Gold ore mixture is fed into the float banks to obtain rougher Au concentrate and rougher tails (product residues with a low concentration of valuable metals). The stability of this process is affected by the volatile and non-optimal physicochemical state of the flotation pulp (a mixture of solid particles and liquid).
### Purification
The rougher concentrate undergoes two stages of purification. After purification, we have the final concentrate and new tails.
## Evaluation metric
To solve the problem, we will need a new metric. It is called $sMAPE$, symmetric Mean Absolute Percentage Error.
It is similar to MAE, but is expressed in relative values instead of absolute ones. Why is it symmetrical? It equally takes into account the scale of both the target and the prediction.
Here’s how $sMAPE$ is calculated:

$sMAPE = \frac{1}{N}$ $\Sigma_{i=1}^N$ $\frac{|y_i-\hat{y}_i|}{(|y_i|+|\hat{y}_i|)/2} \cdot100$ %

Denotation:
- $y_i$ - value of target for the observation with the i index in the sample used to measure quality.
- $\hat{y_i}$ - value of prediction for the observation with the i index, for example, in the test sample.
- $N$ - number of observations in the sample.
- $\Sigma_{i=1}^N$ - summation over all observations of the sample (i takes values from 1 to N).

We need to predict two values:
- rougher concentrate recovery ```rougher.output.recovery```
- final concentrate recovery ```final.output.recovery```

The final metric includes the two values:

$Final$ $sMAPE = 25$%$\times sMAPE(rougher) + 75$%$\times sMAPE(final)$ 

## Project stages:
-  Data preparation
-  Perform data analysis
-  Develop and train a model

The project uses documentation from pandas, matplotlib and sklearn.
