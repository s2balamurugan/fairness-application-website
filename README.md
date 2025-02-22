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
1. Classification loss ensures pseudo_Y aligns with Y.
2. Adversarial loss forces pseudo_Y to be independent of S by minimizing adversary accuracy.
3. Decoder loss ensures Y_pred remains an accurate and fair prediction of Y.

Overall, this adversarial learning approach guarantees fair and accurate predictions by systematically removing biased dependencies while retaining necessary information.

In the left graph below, X is the covariate, Y is the label, Z is the confounder, S is the proxy, taken from Parjanya’s Paper. The right graph is the adjusted node graph to represent our model which includes the sensitive feature. In this graph, X is the covariate, S is the sensitive feature, pseudo Y is the independent Y label of S, Y final is the final fair label predicted from S and pseudo Y. In both graphs, the shaded circles represent unobserved variables and the unshaded ones represent observed variables.

<img width="195" alt="Screen Shot 2025-02-22 at 12 36 38 PM" src="https://github.com/user-attachments/assets/689d4adc-11ef-413c-a99f-008e6a58f28b" />




### Datasets Implemented 
We implemented three datasets, UCI Adult, German Credit and COMPAS dataset. 

The UCI Adult dataset is derived from the U.S. Census Bureau, it predicts whether an individual earns more than $50,000 annually based on factors like age, education, occupation, and work hours. Due to its reflection of real-world income inequalities, it is widely used in fairness and bias research as a benchmark for classification models.

The German Credit dataset is provided by the UCI Machine Learning Repository, it assesses credit risk by categorizing applicants as “good” or “bad” credit risks. It includes features like work status, financial history, home situation, and personal demographics (age, sex, etc.). The dataset is crucial in evaluating bias in financial decision-making and credit scoring models.

The COMPAS dataset is collected by ProPublica, it predicts recidivism risk (reoffending probability) using features such as age, sex, race, past crimes, and COMPAS risk scores. Research has shown racial disparities in risk assessment, making it central to discussions on algorithmic fairness and bias in the criminal justice system.

## Results
need to add



## Conclusion
Our work focuses on developing a fairness-aware algorithm that discovers latent variables to mitigate biases in predictive models. By leveraging an encoder-decoder framework with adversarial biasing, we ensure that sensitive attributes do not unfairly influence predictions while preserving meaningful patterns in the data. Our approach is evaluated on well-established fairness datasets, demonstrating its ability to produce fair and unbiased labels. As data-driven decision-making continues to shape critical domains like healthcare and criminal justice, our method provides a robust solution for addressing structural biases and enhancing the trustworthiness of AI systems.

In the future we will focus on enhancing the model’s adaptability to more complex scenarios. This includes improving its performance when the sensitive feature is non-binary, ensuring it remains effective across diverse demographic groups. Additionally, we aim to extend the model’s capability to handle multi-class observed labels, making it applicable to a broader range of classification tasks. Finally, we will establish clear guidelines for determining when to prioritize accuracy over independence and vice versa, helping users make informed decisions based on their specific fairness and performance requirements.

## Refrences
Choi, YooJung, Meihua Dang, and Guy Van den Broeck. 2020. “Group Fairness by Probabilistic Modeling with Latent Fair Decisions.” https://arxiv.org/abs/2009.09031 

Prashant, Parjanya, Seyedeh Baharan Khatami, Bruno Ribeiro, and Babak Salimi.2024. “Scalable Out-of-distribution Robustness in the Presence of Unobserved Con-
founders.” https://arxiv.org/abs/2411.19923 







