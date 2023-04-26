# Paper Name: Lime: “Why Should I Trust You?” Explaining the Predictions of Any Classifier

## Motivation

Currently, models are evaluated using accuracy metrics on an available validation dataset.
However, real-world data is often significantly different, and further, the evaluation metric may not be indicative of the product’s goal. Inspecting individual predictions and their
explanations is a worthwhile solution, in addition to such metrics

In critical situations or when deploying a model in real world, it's important to know for users/developers the reasoning of the model's prediction to trust the model and the prediction and also to know which model to deploy in which situation.

In this paper,  they describe two types of trust in this area:

- **Trusting a prediction**
    - *what is it?* - whether a user trusts an individual prediction
    sufficiently to take some action based on it
    - *Solution*: **LIME**, an algorithm that can explain the predictions of any classifier or regressor in a faithful way, by approximating it locally with an interpreter model.
- **Trusting a model**
    - *what is it?* -whether the user trusts a model to behave in reasonable ways if deployed
    - *Solution*: **SP-LIME**, a method that selects a set of representative instances with explanations to address the “trusting the model” problem, via sub-modular optimization.

## Why Explanation is needed?

To know if the following is happening while predicting:

- **Data leakage**
    - when the data you are using to train a machine learning algorithm happens to have the information you are trying to predict
- **Dataset shift**
    - when the joint distribution of inputs and outputs differs between training and test stages

## Criteria for Explainers

- **Interpretable**
    - Explanations should be easy to understand, which is not necessarily true of the features used by the model, and thus the “input variables” in the explanations may need to be different than the features
- **Local Fidelity**
    - An explanation to be meaningful it must at least be locally faithful, i.e. it must correspond to how the model behaves in the vicinity of the instance being predicted. Which means, it can tell which factors contributed to the prediction for the current input (this means local), where as it may not be able to tell all the factors that contribute to this prediction output (global)
- **Model Agnostic**
    - An explainer should be able to explain any mode

### **L**ocal **I**nterpretable **M**odel-agnostic **E**xplanations (LIME)

![Untitled](Paper%20Name%20Lime%20%E2%80%9CWhy%20Should%20I%20Trust%20You%20%E2%80%9D%20Explaini%20632c76dd27de4372af444df748faa662/Untitled.png)