# explore-solutions-to-handle-sudden-drift-due-to-covid

## Overview

Drifts are generally of 3 types. <br>

* Gradual drift - happens naturally as a change in user behaviors over time
* Cyclic drift - occurs due to seasonal effects
* Sudden drift - happens due to unexpected events with a large-scale impact changing user behaviors in days to weeks.<br/><br/>
Retraining model periodically or based on drift detection techniques is generally sufficient to handle gradual and cyclic drift. But to handle sudden drift, retraining the model may not be enough since the model is not trained on an adequate amount of data on the new behavior patterns. In this notebook, we will explore a few of the solutions to handle sudden drift and compare them.<br/>


## Solutions explored

* Is retraining the model based on model performance decay and drift detection sufficient?
* Retrain model with instance weightage. Give higher weight to the most recent training examples and least to the oldest. Instance weights can be generated using exponential decay for example.

* Retrain model with the adaptive window. Use only the last 12 months data to train a model. For example
* Retrain model with adaptive window and exponential decay based instance weightage
* Generate synthetic data based on newly available behavior patterns and retrain the model

## Model decay plots


## Conclusions

##### Overall best performance was retraining model with exponential decay based instance weights. Instance weights based solution works well for gradual model decay which is expected over time.
##### Best at handling sudden drift(sharp model decay) during covid was adaptive window solution. Adaptive window solution uses recent data as a result likey to capture more relevant patterns.


