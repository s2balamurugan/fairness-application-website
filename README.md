# Exploration and Applications of Fairness Algorithms
This project is by Lina Batikkha and Sai Poornasree Balamurugan

## Problem Statement and Motivation 
Bias in machine learning models is an issue, especially in areas like incarceration, where decisions can affect an individual’s life. Incarceration data has been shaped by inequalities due to race and socioeconomic states. This results in biased outcomes in predictive models. Addressing this challenge is not just a technical task but a necessity. We aim to incorporate latent variables representing fair decisions to mitigate these biases. We hope to create models that are not only fair but also more interpretable and robust

## What is Latent Variable Modeling?
Latent variable modeling involves the identification and characterization of hidden variables that influence the distribution and outcomes of observed data. These variables are not explicitly provided in the dataset but can be inferred by analyzing patterns and relationships among the observed features. By uncovering latent variables, researchers gain insights into underlying structures and dependencies within the data, enabling more accurate modeling, improved predictions, and a deeper understanding of complex systems.

## Key Research Papers 
In order to investigate fairness in machine learning models, we were inspired by the paper in Group Fairness by Probabilistic Modeling with Latent Fair Decisions by YooJung Choi, Meihua Dang, and Guy Van den Broeck Choi, Dang and den Broeck (2020). This paper addresses the issue of bias in machine learning models, which often discriminate against specific demographic groups due to biased training data. To mitigate this, the authors introduce a latent variable, Df, representing true, unbiased decisions independent of sensitive attributes S. The proposed approach employs a probabilistic model that captures the relationships among fair decisions (Df), biased observed labels (D), sensitive attributes (S), and other non-sensitive features (X). This modeling is achieved using probabilistic circuits (PCs), a type of graphical model that efficiently represents joint probability distributions while enabling tractable inference.

## Objectives
1. 


