# MLOps (machine learning operations)
Definition: Includes the culmination of people, processes, practices and underpinning technologies that automate the deployment, monitoring, and management of machine learning (ML) models into production in a scalable and fully governed way to finally provide measurable business value from machine learning.



# MLOps infrastructure
Can be represented by something as simple as a set of vetted and maintained processes. For example:

* How models are created, trained and approved
* Where models are stored
* How models are deployed
* How models are evaluated and monitored in production
* How models are either corrected or removed from the production environment to minimize risks
* How these processes repeat and intertwine to enable a cyclical machine learning operations process


# [Data science steps for ML](https://cloud.google.com/architecture/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning#data_science_steps_for_ml)
In any ML project, after you define the business use case and establish the success criteria, the process of delivering an ML model to production involves the following steps. These steps can be completed manually or can be completed by an automatic pipeline.

1. Data extraction: You select and integrate the relevant data from various data sources for the ML task.
2. Data analysis: You perform exploratory data analysis (EDA) to understand the available data for building the ML model. This process leads to the following:
    * Understanding the data schema and characteristics that are expected by the model.
    * Identifying the data preparation and feature engineering that are needed for the model.
3. Data preparation: The data is prepared for the ML task. This preparation involves data cleaning, where you split the data into training, validation, and test sets. You also apply data transformations and feature engineering to the model that solves the target task. The output of this step are the data splits in the prepared format.
4. Model training: The data scientist implements different algorithms with the prepared data to train various ML models. In addition, you subject the implemented algorithms to hyperparameter tuning to get the best performing ML model. The output of this step is a trained model.
5. Model evaluation: The model is evaluated on a holdout test set to evaluate the model quality. The output of this step is a set of metrics to assess the quality of the model.
6. Model validation: The model is confirmed to be adequate for deployment—that its predictive performance is better than a certain baseline.
7. Model serving: The validated model is deployed to a target environment to serve predictions. This deployment can be one of the following:
    * Microservices with a REST API to serve online predictions.
    * An embedded model to an edge or mobile device.
    * Part of a batch prediction system.
9. Model monitoring: The model predictive performance is monitored to potentially invoke a new iteration in the ML process.