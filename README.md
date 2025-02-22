# Exploration and Applications of Fairness Algorithms
This project is by Lina Batikkha and Sai Poornasree Balamurugan

## Introduction
Bias in machine learning models is an issue, especially in areas like incarceration, where decisions can affect an individual’s life. Incarceration data has been shaped by inequalities due to race and socioeconomic states. This results in biased outcomes in predictive models. Addressing this challenge is not just a technical task but a necessity. We aim to incorporate latent variables representing fair decisions to mitigate these biases. We hope to create models that are not only fair but also more interpretable and robust

Latent variable modeling involves the identification and characterization of hidden variables that influence the distribution and outcomes of observed data. These variables are not explicitly provided in the dataset but can be inferred by analyzing patterns and relationships among the observed features. By uncovering latent variables, researchers gain insights into underlying structures and dependencies within the data, enabling more accurate modeling, improved predictions, and a deeper understanding of complex systems.


## Methods
Our approach follows an encoder-decoder methodology similar to prior work on out-of-distribution robustness and group fairness to establish independence between the sensitive feature (S) and the fair label (Y_f). Given a dataset with sensitive feature (S), observed label (Y), and non-confounding features (X), we treat Y as a proxy variable to derive the fair label Y_f.

The model consists of three main components:
1. Encoder: Generates an intermediate label (pseudo_Y) from X, which will later be de-biased from S.
2. Adversarial Branch: Uses an adversary and a Gradient Reversal Layer (GRL) to remove unfair dependencies of S from pseudo_Y, ensuring independence between them.
3. Decoder: Predicts Y using both pseudo_Y and S, ensuring that only fair dependencies on S are retained for accurate and unbiased predictions.

The model optimizes three loss functions:
1. Classification loss (Binary/Categorical Cross-Entropy) ensures pseudo_Y aligns with Y.
2. Adversarial loss forces pseudo_Y to be independent of S by minimizing adversary accuracy.
3. Decoder loss ensures Y_pred remains an accurate and fair prediction of Y.

Overall, this adversarial learning approach guarantees fair and accurate predictions by systematically removing biased dependencies while retaining necessary information.

## Results

## Conclusion



## Key Research Papers 
In order to investigate fairness in machine learning models, we were inspired by the paper in Group Fairness by Probabilistic Modeling with Latent Fair Decisions by YooJung Choi, Meihua Dang, and Guy Van den Broeck Choi, Dang and den Broeck (2020). This paper addresses the issue of bias in machine learning models, which often discriminate against specific demographic groups due to biased training data. To mitigate this, the authors introduce a latent variable, Df, representing true, unbiased decisions independent of sensitive attributes S. The proposed approach employs a probabilistic model that captures the relationships among fair decisions (Df), biased observed labels (D), sensitive attributes (S), and other non-sensitive features (X). This modeling is achieved using probabilistic circuits (PCs), a type of graphical model that efficiently represents joint probability distributions while enabling tractable inference.

## Objectives
1. 


