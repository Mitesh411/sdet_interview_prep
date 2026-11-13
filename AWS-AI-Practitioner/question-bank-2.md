# AWS Certified AI Practitioner (AIF-C01): Question Bank 2

> **Last reviewed:** 2026-11-13 against the AIF-C01 exam guide (v1.4) · AI-assisted structural and staleness review · see [review-log.md](review-log.md)
>
> **Question Bank 2** complements Question Bank 1 ([ch1-2.md](ch1-2.md), [ch3-4.md](ch3-4.md), [ch5.md](ch5.md)). 52 questions that repeated Bank 1 were removed in the 2026-11-13 review, so the two banks together give 998 distinct questions.

**473 original practice questions** across the five AIF-C01 exam domains, with correct answers and explanations.

## How to Use This Question Bank

- Work through one domain at a time, or jump between domains to mix topics.
- Cover the **Answer** and **Explanation** lines, answer first, then check yourself.
- Each question is labeled with its domain, type, and difficulty level.
- Question types: **Multiple Choice** (one correct answer), **Multiple Response** (select TWO), and **True/False**.
- Difficulty: **Easy** (recall of definitions), **Medium** (application and comparison), **Hard** (scenario-based reasoning).
- Review every explanation, including for questions you got right. The explanations also describe why the other options are wrong where that is useful.
- A complete answer key is at the end of the document.

> Note: AWS services and features change over time. Verify current details in the official AWS documentation and the current AIF-C01 exam guide before your exam. These questions are original study material and are not actual exam questions.

## Contents

| Domain | Questions |
|---|---|
| [Domain 1: Fundamentals of AI and ML](#domain-1-fundamentals-of-ai-and-ml) | 93 |
| [Domain 2: Fundamentals of Generative AI](#domain-2-fundamentals-of-generative-ai) | 90 |
| [Domain 3: Applications of Foundation Models](#domain-3-applications-of-foundation-models) | 96 |
| [Domain 4: Guidelines for Responsible AI](#domain-4-guidelines-for-responsible-ai) | 98 |
| [Domain 5: Security, Compliance, and Governance](#domain-5-security-compliance-and-governance) | 96 |
| [Answer Key](#answer-key) | All domains |

## Question Bank Summary

| Domain | Total | Multiple Choice | Multiple Response | True/False | Easy | Medium | Hard |
|---|---|---|---|---|---|---|---|
| Domain 1: Fundamentals of AI and ML | 93 | 84 | 2 | 7 | 27 | 58 | 8 |
| Domain 2: Fundamentals of Generative AI | 90 | 79 | 1 | 10 | 13 | 71 | 6 |
| Domain 3: Applications of Foundation Models | 96 | 83 | 4 | 9 | 2 | 78 | 16 |
| Domain 4: Guidelines for Responsible AI | 98 | 88 | 3 | 7 | 5 | 84 | 9 |
| Domain 5: Security, Compliance, and Governance | 96 | 84 | 5 | 7 | 2 | 84 | 10 |
| **Total** | **473** | **418** | **15** | **40** | **49** | **375** | **49** |

---

## Domain 1: Fundamentals of AI and ML

### D1-001
*True/False | Easy*

**Question:** Machine learning models learn patterns from data rather than being explicitly programmed with fixed rules for every case.

- A. True
- B. False

**Answer:** True

**Explanation:** This is the core idea of ML. Algorithms generalize from training examples to make predictions on new data, instead of relying on hand-written if-then logic.

### D1-002
*Multiple Choice | Easy*

**Question:** A bank wants to predict whether a loan applicant will default (yes or no) using historical labeled data. Which type of ML problem is this?

- A. Clustering
- B. Dimensionality reduction
- C. Linear regression
- D. Binary classification

**Answer:** D

**Explanation:** Predicting one of two discrete categories is binary classification, a supervised task. Regression predicts continuous values, while clustering and dimensionality reduction are unsupervised techniques.

### D1-003
*Multiple Choice | Easy*

**Question:** Which task is an example of regression?

- A. Labeling images as cat or dog
- B. Grouping customers by purchasing behavior
- C. Predicting the sale price of a house
- D. Detecting whether an email is spam

**Answer:** C

**Explanation:** Regression predicts a continuous numeric value such as a price. Spam detection and cat/dog labeling are classification, and grouping customers is clustering.

### D1-004
*Multiple Choice | Easy*

**Question:** Which learning type trains on data where every example includes the correct output?

- A. Supervised learning
- B. Self-organizing learning
- C. Unsupervised learning
- D. Reinforcement learning

**Answer:** A

**Explanation:** Supervised learning uses input-label pairs so the model learns a mapping from inputs to known outputs. Unsupervised learning has no labels, and reinforcement learning learns from rewards.

### D1-005
*Multiple Choice | Easy*

**Question:** A retailer wants to discover natural customer segments without any predefined labels. Which approach fits best?

- A. Unsupervised clustering
- B. Supervised classification
- C. Linear regression
- D. Reinforcement learning

**Answer:** A

**Explanation:** Clustering algorithms such as k-means find groupings in unlabeled data. This is unsupervised learning, because no target variable is provided.

### D1-006
*Multiple Choice | Medium*

**Question:** An agent learns to play a game by taking actions, receiving rewards or penalties, and improving its strategy over time. Which paradigm is this?

- A. Transfer learning
- B. Unsupervised learning
- C. Supervised learning
- D. Reinforcement learning

**Answer:** D

**Explanation:** Reinforcement learning optimizes an agent's policy to maximize cumulative reward through trial-and-error interaction with an environment. No labeled dataset is required.

### D1-007
*Multiple Choice | Medium*

**Question:** Semi-supervised learning is best described as which of the following?

- A. Training across devices without sharing raw data
- B. Training with only unlabeled data
- C. Training with labels generated by a reward function
- D. Training with a small amount of labeled data plus a large amount of unlabeled data

**Answer:** D

**Explanation:** Semi-supervised learning combines a small labeled set with a larger unlabeled set. It is useful when labeling is expensive, as with medical images.

### D1-008
*True/False | Easy*

**Question:** Deep learning uses neural networks with many layers and is especially effective on unstructured data such as images, audio, and text.

- A. True
- B. False

**Answer:** True

**Explanation:** Deep neural networks automatically learn hierarchical features from raw unstructured data. This is why they dominate computer vision, speech, and language tasks.

### D1-009
*Multiple Choice | Easy*

**Question:** Which algorithm is commonly used to estimate the probability of a binary outcome, despite having "regression" in its name?

- A. Logistic regression
- B. Linear regression
- C. Principal component analysis
- D. K-means

**Answer:** A

**Explanation:** Logistic regression applies a sigmoid function to output a probability between 0 and 1, so it is used for classification. Linear regression predicts continuous values.

### D1-010
*Multiple Choice | Medium*

**Question:** Which of the following is an unsupervised dimensionality reduction technique?

- A. Logistic regression
- B. Principal component analysis (PCA)
- C. XGBoost
- D. Support vector machine

**Answer:** B

**Explanation:** PCA projects high-dimensional data onto fewer components that retain most of the variance, and it needs no labels. The other options are supervised algorithms.

### D1-011
*Multiple Choice | Medium*

**Question:** A random forest is an example of which kind of model?

- A. A single deep neural network
- B. A generative adversarial network
- C. A reinforcement learning agent
- D. An ensemble of decision trees

**Answer:** D

**Explanation:** Random forests train many decision trees on random subsets of data and features, then combine their outputs by voting or averaging. This reduces variance compared with a single tree.

### D1-012
*Multiple Choice | Easy*

**Question:** In the k-means algorithm, what does k represent?

- A. The number of nearest neighbors
- B. The number of clusters
- C. The learning rate
- D. The number of input features

**Answer:** B

**Explanation:** K-means partitions data into k clusters, and k must be chosen up front. The nearest-neighbor count is the k in k-NN, which is a different algorithm.

### D1-013
*Multiple Choice | Medium*

**Question:** How does the k-nearest neighbors (k-NN) algorithm make a prediction?

- A. It uses the majority label or average value of the k closest labeled examples
- B. It reduces data to a few principal components
- C. It maximizes a cumulative reward
- D. It fits a linear equation to all training data

**Answer:** A

**Explanation:** k-NN is an instance-based supervised method. It finds the k training points closest to a new point and takes a majority vote for classification or an average for regression.

### D1-014
*True/False | Medium*

**Question:** A decision tree is generally considered more interpretable than a deep neural network.

- A. True
- B. False

**Answer:** True

**Explanation:** Decision trees expose explicit if-then splits that humans can follow. Deep networks have millions of parameters and are much harder to interpret, which is the classic interpretability-versus-performance trade-off.

### D1-015
*Multiple Choice | Medium*

**Question:** A hospital screens patients for a serious disease, and missing a true case is very costly. Which metric should the team prioritize?

- A. Precision
- B. Specificity
- C. Recall (sensitivity)
- D. Mean squared error

**Answer:** C

**Explanation:** Recall measures the share of actual positives that are found. When false negatives are costly, maximize recall even if some false positives result.

### D1-016
*Multiple Choice | Medium*

**Question:** An email spam filter must avoid sending legitimate emails to the spam folder. Which metric matters most?

- A. Perplexity
- B. R-squared
- C. Precision
- D. Recall

**Answer:** C

**Explanation:** Precision is the share of predicted positives that are truly positive. Minimizing false positives (legitimate mail flagged as spam) means maximizing precision.

### D1-017
*Multiple Choice | Easy*

**Question:** What is the F1 score?

- A. The harmonic mean of precision and recall
- B. The error rate on the validation set
- C. The arithmetic mean of accuracy and recall
- D. The ratio of true negatives to all negatives

**Answer:** A

**Explanation:** F1 balances precision and recall in one number. The harmonic mean penalizes models where either value is very low.

### D1-018
*Multiple Choice | Medium*

**Question:** What does the AUC-ROC metric measure for a classifier?

- A. How well the model separates classes across all classification thresholds
- B. The training time per epoch
- C. The average squared prediction error
- D. The number of features used

**Answer:** A

**Explanation:** The ROC curve plots true positive rate against false positive rate at varying thresholds. AUC summarizes it, where 1.0 is perfect separation and 0.5 is random guessing.

### D1-019
*Multiple Choice | Easy*

**Question:** Which metric is commonly used to evaluate regression models?

- A. AUC-ROC
- B. Root mean squared error (RMSE)
- C. F1 score
- D. Precision

**Answer:** B

**Explanation:** RMSE measures the typical size of prediction errors in the target's own units. Precision, F1, and AUC apply to classification.

### D1-020
*Multiple Choice | Medium*

**Question:** In a confusion matrix, what is a false negative?

- A. The model predicts positive and the actual class is negative
- B. The model predicts negative and the actual class is positive
- C. The model predicts positive and the actual class is positive
- D. The model predicts negative and the actual class is negative

**Answer:** B

**Explanation:** A false negative is a missed positive: the real class is positive but the model said negative. A false positive is the opposite error.

### D1-021
*Multiple Choice | Medium*

**Question:** Compared with mean absolute error (MAE), RMSE does which of the following?

- A. Ignores outliers completely
- B. Penalizes large errors more heavily
- C. Can only be used for classification
- D. Always produces a smaller value

**Answer:** B

**Explanation:** Squaring errors before averaging gives large mistakes disproportionate weight. RMSE is therefore more sensitive to outliers than MAE.

### D1-022
*Multiple Choice | Hard*

**Question:** A classifier produces TP = 80, FP = 20, FN = 40, TN = 860. What is the precision?

- A. 0.67
- B. 0.92
- C. 0.33
- D. 0.80

**Answer:** D

**Explanation:** Precision = TP / (TP + FP) = 80 / 100 = 0.80. Recall for the same data would be 80 / 120, about 0.67.

### D1-023
*Multiple Choice | Hard*

**Question:** A classifier produces TP = 80, FP = 20, FN = 40, TN = 860. What is the recall?

- A. 0.67
- B. 0.92
- C. 0.33
- D. 0.80

**Answer:** A

**Explanation:** Recall = TP / (TP + FN) = 80 / 120, about 0.67. The value 0.80 is the precision, and 0.33 is the miss rate.

### D1-024
*Multiple Choice | Easy*

**Question:** What is overfitting?

- A. The model uses too few hyperparameters
- B. The model performs well on training data but poorly on new, unseen data
- C. The model trains too quickly
- D. The model performs poorly on both training and new data

**Answer:** B

**Explanation:** An overfit model memorizes noise and specifics of the training set, so it fails to generalize. A large gap between training and validation performance is the typical sign.

### D1-025
*Multiple Choice | Easy*

**Question:** What is underfitting?

- A. The model memorizes the training set
- B. The model is too simple to capture the underlying pattern and performs poorly even on training data
- C. The model was trained on too much data
- D. The model has too many parameters

**Answer:** B

**Explanation:** Underfitting means high bias. The model cannot capture the signal, so error is high on both training and validation data.

### D1-026
*Multiple Choice | Medium*

**Question:** A model shows high error on both the training set and the validation set. What is the most likely issue?

- A. High bias (underfitting)
- B. Data leakage
- C. Class imbalance only
- D. High variance

**Answer:** A

**Explanation:** High error on both sets indicates the model is too simple or under-trained, which is high bias. Remedies include more features, a more complex model, or longer training.

### D1-027
*Multiple Choice | Medium*

**Question:** A model shows very low training error but much higher validation error. What does this indicate?

- A. High bias
- B. Underfitting
- C. High variance (overfitting)
- D. A good generalization

**Answer:** C

**Explanation:** A large train/validation gap signals high variance. The model has fit the training data too closely.

### D1-028
*Multiple Choice | Easy*

**Question:** What is the purpose of the held-out test set?

- A. To provide a final, unbiased estimate of performance on unseen data
- B. To tune hyperparameters
- C. To label the data
- D. To increase the amount of training data

**Answer:** A

**Explanation:** The test set must stay untouched until the end so that it gives an honest estimate of real-world performance. Using it for tuning contaminates that estimate.

### D1-029
*Multiple Choice | Medium*

**Question:** What is the purpose of the validation set?

- A. To compare models and tune hyperparameters during development
- B. To replace the training set
- C. To be the final report of accuracy
- D. To store production predictions

**Answer:** A

**Explanation:** The validation set guides model selection and hyperparameter tuning without touching the test set.

### D1-030
*Multiple Choice | Medium*

**Question:** Which scenario is an example of data leakage?

- A. Removing duplicate rows
- B. Splitting data randomly into train and test sets
- C. Using cross-validation
- D. Computing normalization statistics on the entire dataset before splitting, or including a feature derived from the target

**Answer:** C

**Explanation:** Leakage happens when information from outside the training data, such as test data or the target itself, influences training. It yields overly optimistic results that fail in production.

### D1-031
*Multiple Choice | Medium*

**Question:** Why is k-fold cross-validation used?

- A. To label unlabeled data
- B. To increase the size of the dataset artificially
- C. To obtain a more reliable estimate of generalization by training and validating on multiple data splits
- D. To speed up inference

**Answer:** C

**Explanation:** Cross-validation rotates which fold is held out for validation, so every record is used for both training and validation. This reduces dependence on one particular split.

### D1-032
*Multiple Choice | Easy*

**Question:** What is feature engineering?

- A. Deploying a model to an endpoint
- B. Creating, selecting, or transforming input variables to improve model performance
- C. Writing unit tests for the model
- D. Choosing the cloud region

**Answer:** B

**Explanation:** Examples include creating ratios, extracting date parts, encoding categories, and scaling values. Good features often improve a model more than switching algorithms.

### D1-033
*Multiple Choice | Medium*

**Question:** Which is an example of time-series data?

- A. A list of unrelated product categories
- B. A folder of product photos
- C. A set of customer survey free-text comments
- D. Temperature readings logged from an IoT sensor every second

**Answer:** D

**Explanation:** Time-series data is a sequence of observations indexed by time. Order matters, which affects how it is split for training and testing.

### D1-034
*Multiple Choice | Medium*

**Question:** Which technique can help with a highly imbalanced training dataset?

- A. Removing all features
- B. Oversampling the minority class (for example, with SMOTE) or undersampling the majority class
- C. Increasing the learning rate to the maximum
- D. Using only the test set

**Answer:** A

**Explanation:** Resampling techniques rebalance class representation. Class weights and suitable metrics such as F1 or AUC also help.

### D1-035
*Multiple Choice | Medium*

**Question:** What is a common way to handle missing values in a numeric column?

- A. Changing the label
- B. Deleting the model
- C. Imputing them (for example, with the mean or median) or dropping affected rows when appropriate
- D. Duplicating the entire dataset

**Answer:** C

**Explanation:** Imputation fills gaps using statistics or models, preserving rows. The right choice depends on how much data is missing and why.

### D1-036
*Multiple Choice | Medium*

**Question:** Why are numeric features often normalized or standardized before training?

- A. To convert numbers to text
- B. To remove labels
- C. To increase the number of rows
- D. To make features with different scales contribute comparably, which helps many algorithms converge

**Answer:** D

**Explanation:** Distance-based and gradient-based algorithms are sensitive to feature scale. Scaling prevents large-valued features from dominating.

### D1-037
*Multiple Choice | Medium*

**Question:** What does one-hot encoding do?

- A. Removes outliers
- B. Reduces the number of rows
- C. Converts a categorical variable into binary indicator columns, one per category
- D. Normalizes numeric values between 0 and 1

**Answer:** C

**Explanation:** A category such as color with values red, green, and blue becomes three 0/1 columns. This lets algorithms use categorical data without imposing a false order.

### D1-038
*True/False | Medium*

**Question:** More training data always guarantees a better model, regardless of data quality.

- A. True
- B. False

**Answer:** False

**Explanation:** Quality, relevance, and representativeness matter as much as quantity. Noisy, biased, or mislabeled data can degrade a model no matter how much of it there is.

### D1-039
*Multiple Choice | Medium*

**Question:** A fraud model's input feature distributions in production gradually differ from those seen in training. What is this called?

- A. Regularization
- B. Label noise
- C. Overfitting
- D. Data drift

**Answer:** D

**Explanation:** Data (covariate) drift is a change in the distribution of input data over time. It can reduce accuracy, so it should be monitored and may trigger retraining.

### D1-040
*Multiple Choice | Hard*

**Question:** The relationship between inputs and the target changes over time, for example, customer behavior shifts after a pandemic. What is this called?

- A. Data leakage
- B. Concept drift
- C. Feature scaling
- D. Underfitting

**Answer:** B

**Explanation:** Concept drift means the mapping from features to target has changed, so a previously accurate model becomes outdated even if input distributions look similar.

### D1-041
*Multiple Choice | Medium*

**Question:** Which sequence best reflects the typical ML lifecycle?

- A. Define the business problem, collect and prepare data, engineer features, train, evaluate, deploy, monitor
- B. Deploy, train, collect data, define problem
- C. Train, define the problem, deploy, collect data
- D. Evaluate, collect data, deploy, train

**Answer:** A

**Explanation:** The lifecycle is iterative, and monitoring often feeds back into further data collection, retraining, and redeployment.

### D1-042
*Multiple Choice | Medium*

**Question:** For which problem is machine learning probably NOT the right choice?

- A. Detecting anomalies in network traffic
- B. Computing sales tax from a fixed published rate table
- C. Recommending products to millions of users
- D. Forecasting product demand

**Answer:** B

**Explanation:** When deterministic rules solve the problem exactly and fully, ML adds cost and uncertainty without benefit. ML suits tasks where patterns are complex or too hard to hand-code.

### D1-043
*Multiple Choice | Medium*

**Question:** What is MLOps?

- A. A pricing model for GPUs
- B. A type of neural network
- C. Practices that apply DevOps principles to automate, deploy, monitor, and govern ML workflows
- D. A programming language for ML

**Answer:** C

**Explanation:** MLOps covers CI/CD for ML, reproducibility, model versioning, monitoring, and retraining. It brings reliability and speed to moving models into production.

### D1-044
*Multiple Choice | Medium*

**Question:** Why should deployed models be monitored continuously?

- A. Monitoring is only required for regulatory reasons
- B. To detect drift and performance degradation as real-world data and behavior change
- C. Models never change after deployment
- D. To reduce training data size

**Answer:** B

**Explanation:** Production data evolves. Monitoring catches data drift, concept drift, and bias drift so teams can retrain or fix the model.

### D1-045
*Multiple Choice | Easy*

**Question:** What is an epoch in neural network training?

- A. A type of activation function
- B. One complete pass through the entire training dataset
- C. The size of a mini-batch
- D. A single prediction request

**Answer:** B

**Explanation:** Models typically train for many epochs, and each epoch lets the model see all training examples once.

### D1-046
*Multiple Choice | Medium*

**Question:** What is the role of a loss function?

- A. It deploys the model
- B. It quantifies how far the model's predictions are from the true values, guiding optimization
- C. It encrypts the data
- D. It splits the dataset

**Answer:** B

**Explanation:** Training seeks to minimize the loss. Examples include mean squared error for regression and cross-entropy for classification.

### D1-047
*Multiple Choice | Medium*

**Question:** What does gradient descent do?

- A. Splits data into folds
- B. Labels the dataset automatically
- C. Selects the best cloud region
- D. Iteratively adjusts model parameters in the direction that reduces the loss

**Answer:** D

**Explanation:** Gradient descent computes the gradient of the loss with respect to the parameters and updates the parameters in small steps (scaled by the learning rate) to reduce error.

### D1-048
*Multiple Choice | Medium*

**Question:** Why are non-linear activation functions used in neural networks?

- A. They let networks learn complex, non-linear relationships
- B. They replace the loss function
- C. They reduce the amount of data needed
- D. They encrypt intermediate values

**Answer:** A

**Explanation:** Without non-linear activations, stacked layers collapse into a single linear transformation. Functions such as ReLU add the expressive power for complex patterns.

### D1-049
*Multiple Choice | Medium*

**Question:** What key mechanism lets transformer models weigh the relevance of different parts of an input sequence?

- A. One-hot encoding
- B. Pooling
- C. Dropout
- D. Self-attention

**Answer:** D

**Explanation:** Self-attention computes how much each token should attend to every other token, which captures long-range context and allows parallel processing.

### D1-050
*Multiple Choice | Medium*

**Question:** What is transfer learning?

- A. Moving data between AWS Regions
- B. Transferring ownership of a model
- C. Copying a dataset to a new bucket
- D. Reusing a model trained on one task as the starting point for a related task

**Answer:** D

**Explanation:** Starting from pretrained weights lets you reach good accuracy with less data and compute. Fine-tuning a pretrained model is a common form of transfer learning.

### D1-051
*Multiple Choice | Easy*

**Question:** What is Amazon SageMaker?

- A. A relational database engine
- B. A DNS service
- C. A content delivery network
- D. A managed service for building, training, and deploying machine learning models at scale

**Answer:** D

**Explanation:** SageMaker provides tools across the ML lifecycle, from data prep and training to hosting and monitoring, without managing the underlying infrastructure.

### D1-052
*Multiple Choice | Easy*

**Question:** Which SageMaker capability lets business analysts build ML models and generate predictions with a visual, no-code interface?

- A. SageMaker Neo
- B. SageMaker Canvas
- C. SageMaker Debugger
- D. SageMaker Pipelines

**Answer:** B

**Explanation:** Canvas offers a point-and-click interface for importing data, building models, and generating predictions without writing code.

### D1-053
*Multiple Choice | Medium*

**Question:** Which SageMaker feature automatically builds, trains, and tunes candidate models for tabular data while giving visibility into how they were created?

- A. SageMaker Model Monitor
- B. SageMaker Feature Store
- C. SageMaker Ground Truth
- D. SageMaker Autopilot

**Answer:** D

**Explanation:** Autopilot is SageMaker's AutoML capability. It explores data preprocessing, algorithms, and hyperparameters, and it provides notebooks that show what it did.

### D1-054
*Multiple Choice | Easy*

**Question:** Which SageMaker tool helps import, analyze, transform, and prepare data for ML with little code?

- A. SageMaker Clarify
- B. SageMaker Data Wrangler
- C. SageMaker Debugger
- D. SageMaker Neo

**Answer:** B

**Explanation:** Data Wrangler simplifies data preparation and feature engineering through a visual interface with built-in transforms and analyses.

### D1-055
*Multiple Choice | Medium*

**Question:** What is the purpose of SageMaker Feature Store?

- A. Detecting drift in production
- B. A central repository to store, share, and reuse features for training and inference, with online and offline stores
- C. Compiling models for edge devices
- D. Labeling images with human workers

**Answer:** B

**Explanation:** Feature Store keeps features consistent between training and real-time inference, which reduces training/serving skew and duplicated feature work.

### D1-056
*Multiple Choice | Easy*

**Question:** Which service helps create high-quality labeled training datasets using human annotators and automated labeling?

- A. SageMaker Ground Truth
- B. Amazon Kendra
- C. AWS Glue
- D. Amazon Comprehend

**Answer:** A

**Explanation:** Ground Truth manages data labeling workflows with public, private, or vendor workforces and can use active learning to reduce labeling cost.

### D1-057
*Multiple Choice | Medium*

**Question:** Which SageMaker feature detects bias in data and models and explains individual predictions using feature attributions?

- A. SageMaker Pipelines
- B. SageMaker JumpStart
- C. SageMaker Clarify
- D. SageMaker Debugger

**Answer:** C

**Explanation:** Clarify computes pre-training and post-training bias metrics and generates explainability reports (for example, SHAP values).

### D1-058
*Multiple Choice | Medium*

**Question:** Which SageMaker feature orchestrates ML workflows as automated, repeatable pipelines with CI/CD support?

- A. SageMaker Canvas
- B. SageMaker Clarify
- C. SageMaker Ground Truth
- D. SageMaker Pipelines

**Answer:** D

**Explanation:** Pipelines defines steps such as processing, training, evaluation, and registration as a directed graph, enabling MLOps automation.

### D1-059
*Multiple Choice | Medium*

**Question:** What does the SageMaker Model Registry provide?

- A. Automatic hyperparameter search
- B. GPU capacity reservations
- C. Real-time labeling of images
- D. A catalog of model versions with metadata and approval status for governed deployment

**Answer:** D

**Explanation:** The registry tracks model versions, lineage, and approval states (for example, pending or approved), which supports controlled promotion to production.

### D1-060
*Multiple Choice | Easy*

**Question:** What is SageMaker JumpStart?

- A. A hub of pretrained models, including foundation models, and solution templates that can be deployed or fine-tuned quickly
- B. A network firewall
- C. A tool to encrypt data
- D. A billing dashboard

**Answer:** A

**Explanation:** JumpStart accelerates starts with prebuilt models and notebooks from public hubs and providers, which reduces time to value.

### D1-061
*Multiple Choice | Medium*

**Question:** Which SageMaker feature optimizes and compiles trained models to run efficiently on specific target hardware, including edge devices?

- A. SageMaker Data Wrangler
- B. SageMaker Neo
- C. SageMaker Ground Truth
- D. SageMaker Clarify

**Answer:** B

**Explanation:** Neo compiles models for target processors, which improves inference speed and reduces the memory footprint.

### D1-062
*Multiple Choice | Medium*

**Question:** Which SageMaker capability monitors training jobs in real time and flags problems such as vanishing gradients or overfitting?

- A. SageMaker Feature Store
- B. SageMaker Canvas
- C. SageMaker Debugger
- D. SageMaker Model Registry

**Answer:** C

**Explanation:** Debugger captures tensors and metrics during training and applies built-in rules to detect training issues early.

### D1-063
*Multiple Choice | Medium*

**Question:** A team wants to track and compare many training runs, including parameters and metrics. Which SageMaker capability fits?

- A. SageMaker Experiments
- B. SageMaker Neo
- C. SageMaker Canvas
- D. SageMaker Ground Truth

**Answer:** A

**Explanation:** Experiments organizes and compares trials, including parameters, metrics, and artifacts, which supports reproducibility.

### D1-064
*Multiple Choice | Medium*

**Question:** An application needs low-latency, synchronous predictions from a continuously available endpoint. Which SageMaker inference option fits?

- A. Real-time inference endpoint
- B. Asynchronous inference only
- C. SageMaker Ground Truth
- D. Batch transform

**Answer:** A

**Explanation:** Real-time endpoints are persistent, return responses in milliseconds to seconds, and suit interactive applications.

### D1-065
*Multiple Choice | Medium*

**Question:** Requests have large payloads (hundreds of MB) and long processing times, and clients can wait for results. Which inference option fits?

- A. Edge inference
- B. Batch transform with no S3
- C. Real-time inference
- D. Asynchronous inference

**Answer:** D

**Explanation:** Asynchronous inference queues requests, supports large payloads and long processing, and can scale to zero when idle.

### D1-066
*Multiple Choice | Medium*

**Question:** A workload has intermittent, unpredictable traffic with idle periods and can tolerate cold starts. Which option minimizes cost?

- A. SageMaker Serverless Inference
- B. Dedicated GPU cluster
- C. Always-on real-time endpoint
- D. On-premises server

**Answer:** A

**Explanation:** Serverless Inference scales automatically, including to zero, and you pay only for compute used while requests are processed.

### D1-067
*Multiple Choice | Medium*

**Question:** How can a team reduce the cost of SageMaker training jobs that are fault tolerant?

- A. Use only the largest instance types
- B. Train in multiple Regions at once
- C. Disable checkpointing
- D. Use managed spot training

**Answer:** D

**Explanation:** Managed spot training uses spare EC2 capacity at significant discounts, and checkpoints let jobs resume after interruption.

### D1-068
*Multiple Choice | Medium*

**Question:** Which SageMaker feature automatically searches for the best hyperparameter values by running multiple training jobs?

- A. SageMaker Neo
- B. SageMaker Clarify
- C. SageMaker Ground Truth
- D. Automatic Model Tuning

**Answer:** D

**Explanation:** Automatic Model Tuning (hyperparameter optimization) runs many training jobs with different configurations and finds the best-performing set against an objective metric.

### D1-069
*Multiple Choice | Medium*

**Question:** What do SageMaker Model Cards help teams do?

- A. Document a model's intended use, training data, evaluation results, and risk information for governance
- B. Encrypt model artifacts
- C. Increase GPU memory
- D. Process payments

**Answer:** A

**Explanation:** Model Cards centralize model documentation and support transparency, audits, and responsible AI practices.

### D1-070
*Multiple Choice | Hard*

**Question:** A small team with no data scientists wants to predict customer churn from a tabular CSV with minimal coding effort. Which approach is the best fit?

- A. Build a custom TensorFlow model from scratch
- B. Use SageMaker Canvas, which provides no-code ML for tabular data
- C. Hire a team to write a custom algorithm
- D. Use Amazon Polly

**Answer:** B

**Explanation:** Canvas lets business users import data, auto-build models, and generate predictions without code. Polly is text-to-speech and does not fit.

### D1-071
*Multiple Choice | Easy*

**Question:** Which AWS service analyzes images and videos to detect objects, faces, text, and inappropriate content?

- A. Amazon Comprehend
- B. Amazon Rekognition
- C. Amazon Lex
- D. Amazon Polly

**Answer:** B

**Explanation:** Rekognition is a pretrained computer vision service for object and scene detection, facial analysis and comparison, text in images, and content moderation.

### D1-072
*Multiple Choice | Easy*

**Question:** Which AWS service performs natural language processing tasks such as sentiment analysis, entity recognition, and key phrase extraction?

- A. Amazon Polly
- B. Amazon Comprehend
- C. Amazon Translate
- D. Amazon Transcribe

**Answer:** B

**Explanation:** Comprehend extracts insights from text, including sentiment, entities, language, key phrases, topics, and PII.

### D1-073
*Multiple Choice | Easy*

**Question:** Which AWS service converts text into lifelike speech?

- A. Amazon Polly
- B. Amazon Transcribe
- C. Amazon Rekognition
- D. Amazon Comprehend

**Answer:** A

**Explanation:** Polly is text-to-speech, with neural voices and many languages.

### D1-074
*Multiple Choice | Easy*

**Question:** Which AWS service provides neural machine translation between languages?

- A. Amazon Comprehend
- B. Amazon Transcribe
- C. Amazon Kendra
- D. Amazon Translate

**Answer:** D

**Explanation:** Translate performs real-time and batch translation of text across many language pairs.

### D1-075
*Multiple Choice | Easy*

**Question:** Which AWS service builds conversational interfaces, including chatbots, using voice and text with automatic speech recognition and natural language understanding?

- A. Amazon Polly
- B. Amazon Personalize
- C. Amazon Textract
- D. Amazon Lex

**Answer:** D

**Explanation:** Lex uses the same deep learning technologies that power Alexa, and it handles intents, slots, and dialogue management for bots.

### D1-076
*Multiple Choice | Easy*

**Question:** Which AWS service extracts printed text, handwriting, forms, and tables from scanned documents?

- A. Amazon Rekognition
- B. Amazon Comprehend
- C. Amazon Textract
- D. Amazon Translate

**Answer:** C

**Explanation:** Textract goes beyond simple OCR by identifying the structure of forms and tables and extracting key-value pairs.

### D1-077
*Multiple Choice | Medium*

**Question:** Which AWS service provides intelligent enterprise search using natural language queries across connected data sources?

- A. Amazon Rekognition
- B. Amazon Kendra
- C. Amazon Polly
- D. Amazon Textract

**Answer:** B

**Explanation:** Kendra is an ML-powered search service that returns precise answers and ranked documents from connected repositories. It is also commonly used as a retriever for RAG.

### D1-078
*Multiple Choice | Medium*

**Question:** Which AWS service generates real-time personalized product and content recommendations?

- A. Amazon Translate
- B. Amazon Textract
- C. Amazon Transcribe
- D. Amazon Personalize

**Answer:** D

**Explanation:** Personalize uses the same technology as Amazon.com recommendations and needs no ML expertise to deliver personalized experiences.

### D1-079
*Multiple Choice | Medium*

**Question:** Which service extracts medical conditions, medications, and dosages from unstructured clinical text?

- A. Amazon Comprehend
- B. Amazon Polly
- C. Amazon Comprehend Medical
- D. Amazon Rekognition

**Answer:** C

**Explanation:** Comprehend Medical is a HIPAA-eligible NLP service tailored to clinical text, such as physician notes and discharge summaries.

### D1-080
*Multiple Choice | Medium*

**Question:** Which service adds human review workflows for low-confidence ML predictions?

- A. Amazon SageMaker Neo
- B. Amazon Augmented AI (Amazon A2I)
- C. Amazon Polly
- D. AWS Glue

**Answer:** B

**Explanation:** A2I routes predictions below a confidence threshold, or a random sample, to human reviewers to improve accuracy and provide oversight.

### D1-081
*Multiple Choice | Medium*

**Question:** Which AWS service can analyze customer-agent calls in a contact center to provide sentiment and conversation analytics?

- A. Amazon Polly
- B. Amazon Textract
- C. Amazon Rekognition
- D. Contact Lens for Amazon Connect

**Answer:** D

**Explanation:** Contact Lens for Amazon Connect uses ML to transcribe and analyze calls and chats, providing sentiment, categories, and issue detection.

### D1-082
*Multiple Choice | Medium*

**Question:** Which service uses ML to automate code reviews and identify the most expensive lines of code?

- A. Amazon Transcribe
- B. Amazon Lex
- C. Amazon CodeGuru
- D. Amazon Kendra

**Answer:** C

**Explanation:** CodeGuru Reviewer detects code defects and security issues, and the profiler identifies performance bottlenecks and costly code.

### D1-083
*Multiple Choice | Hard*

**Question:** A social platform needs to automatically flag inappropriate images uploaded by users. Which service is most appropriate?

- A. Amazon Rekognition content moderation
- B. Amazon Translate
- C. Amazon Textract
- D. Amazon Polly

**Answer:** A

**Explanation:** Rekognition content moderation detects explicit or suggestive content in images and videos and returns labels and confidence scores.

### D1-084
*Multiple Choice | Hard*

**Question:** A support team wants to find and redact personally identifiable information (PII) in thousands of text tickets. Which service is the best fit?

- A. Amazon Polly
- B. Amazon Rekognition
- C. Amazon Transcribe
- D. Amazon Comprehend PII detection

**Answer:** D

**Explanation:** Comprehend can detect and redact PII entities such as names, addresses, and phone numbers in text.

### D1-085
*Multiple Choice | Hard*

**Question:** When is a pre-built AWS AI service generally preferable to building a custom model?

- A. When the use case is common, speed to market matters, and the team lacks ML expertise
- B. When training data is plentiful and unique
- C. When the problem is highly unique and needs proprietary architectures
- D. When regulators demand full source code of algorithms

**Answer:** A

**Explanation:** AI services such as Rekognition and Comprehend are pretrained and API-driven. They minimize effort and cost for common tasks, while custom models suit unique problems.

### D1-086
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO AWS services are speech-related? (Select TWO.)

- A. Amazon Kendra
- B. Amazon Textract
- C. Amazon Transcribe
- D. Amazon Comprehend
- E. Amazon Polly

**Answer:** C, E

**Explanation:** Transcribe converts speech to text, and Polly converts text to speech. Textract reads documents, Comprehend analyzes text, and Kendra searches content.

### D1-087
*Multiple Choice | Medium*

**Question:** A manufacturer needs predictions on a camera at a factory with intermittent internet connectivity. Which deployment approach best addresses this?

- A. Sending all images to a central data center
- B. Deploying the model to the edge device so inference runs locally
- C. Only real-time cloud endpoints
- D. Batch transform every month

**Answer:** B

**Explanation:** Edge deployment runs inference on the device, which provides low latency and works when connectivity is unreliable. Models can be optimized with tools such as SageMaker Neo.

### D1-088
*Multiple Choice | Medium*

**Question:** Which statement describes the trade-off between model interpretability and performance?

- A. Simple, interpretable models are often less accurate than complex ones, which are harder to explain
- B. Interpretability always improves accuracy
- C. Complex models are always more interpretable
- D. There is no trade-off

**Answer:** A

**Explanation:** Linear models and shallow trees are easy to explain but may capture fewer patterns. Deep models can achieve higher accuracy at the cost of transparency.

### D1-089
*True/False | Medium*

**Question:** Batch inference is the best choice when predictions are needed within milliseconds for each user click.

- A. True
- B. False

**Answer:** False

**Explanation:** Batch inference processes many records offline with no latency guarantees. Millisecond interactive predictions need real-time inference endpoints.

### D1-090
*Multiple Response (Select TWO) | Hard*

**Question:** Which TWO statements describe unsupervised learning? (Select TWO.)

- A. It optimizes cumulative reward through interaction
- B. It can only be used with images
- C. Clustering and dimensionality reduction are typical tasks
- D. It finds structure in data without labels
- E. It requires a labeled target for every training example

**Answer:** C, D

**Explanation:** Unsupervised learning discovers patterns such as groups or lower-dimensional structure in unlabeled data. Labels indicate supervised learning, and rewards indicate reinforcement learning.

### D1-091
*True/False | Medium*

**Question:** SageMaker Feature Store can help ensure the same feature definitions are used for training and inference.

- A. True
- B. False

**Answer:** True

**Explanation:** A central feature repository with offline and online stores reduces training/serving skew by serving consistent features in both phases.

### D1-092
*Multiple Choice | Medium*

**Question:** Which of the following is an example of narrow (weak) AI?

- A. A spam filter that is only designed to classify emails
- B. A hypothetical system with human-level reasoning across all domains
- C. A system that has consciousness
- D. A system that can learn any intellectual task a human can

**Answer:** A

**Explanation:** Narrow AI performs a specific task. All AI deployed today is narrow, and general AI remains hypothetical.

### D1-093
*True/False | Easy*

**Question:** Reinforcement learning requires a labeled dataset of correct input-output pairs.

- A. True
- B. False

**Answer:** False

**Explanation:** Reinforcement learning learns from reward signals obtained by interacting with an environment, not from labeled examples.

---

## Domain 2: Fundamentals of Generative AI

### D2-001
*True/False | Easy*

**Question:** Generative AI models can create new content, whereas traditional discriminative models mainly classify or predict labels for existing inputs.

- A. True
- B. False

**Answer:** True

**Explanation:** Generative models produce new samples such as text or images, while discriminative models learn decision boundaries between classes or predict values.

### D2-002
*Multiple Choice | Medium*

**Question:** Which neural network architecture underlies most modern LLMs?

- A. Decision tree
- B. K-means
- C. Convolutional neural network
- D. Transformer

**Answer:** D

**Explanation:** Transformers use self-attention to model relationships between all tokens in a sequence and process them in parallel, which enabled the scaling of modern LLMs.

### D2-003
*Multiple Choice | Medium*

**Question:** How do diffusion models generate images?

- A. By iteratively removing noise, starting from random noise, to produce an image guided by learned patterns
- B. By copying images from a database
- C. By clustering pixel colors
- D. By classifying pixels into categories

**Answer:** A

**Explanation:** Diffusion models learn to reverse a gradual noising process. At generation time they start from noise and denoise step by step, often conditioned on a text prompt.

### D2-004
*Multiple Choice | Medium*

**Question:** What is a multimodal model?

- A. A model trained with several GPUs
- B. A model that works only on tabular data
- C. A model that serves multiple customers
- D. A model that can process or generate more than one type of data, such as text and images

**Answer:** D

**Explanation:** Multimodal FMs understand inputs like text, images, audio, or video, and can sometimes generate outputs in multiple modalities, such as describing an image in text.

### D2-005
*Multiple Choice | Medium*

**Question:** Why are tokens important for cost planning with models in Amazon Bedrock?

- A. Tokens control IAM permissions
- B. Tokens only affect image quality
- C. On-demand pricing is typically based on the number of input and output tokens processed
- D. Tokens determine the Region

**Answer:** C

**Explanation:** On-demand pricing for text models is usually charged per 1,000 input and output tokens, so prompt and response lengths directly affect cost.

### D2-006
*Multiple Choice | Medium*

**Question:** How is semantic similarity between two embeddings commonly measured?

- A. By comparing file sizes
- B. By using a distance or similarity metric such as cosine similarity
- C. By comparing timestamps
- D. By comparing character counts

**Answer:** B

**Explanation:** Cosine similarity (or Euclidean distance or dot product) quantifies how close two vectors are, and thus how similar their meanings are.

### D2-007
*Multiple Choice | Easy*

**Question:** What effect does lowering the temperature inference parameter have?

- A. The model runs on cheaper hardware
- B. The context window grows
- C. Output becomes more deterministic and focused
- D. Output becomes more random and creative

**Answer:** C

**Explanation:** Lower temperature sharpens the probability distribution, so the model favors the most likely tokens. This suits factual or structured tasks.

### D2-008
*Multiple Choice | Medium*

**Question:** A marketing team wants more varied, creative taglines from a model. Which setting change is most appropriate?

- A. Increase the temperature
- B. Remove the prompt
- C. Set temperature to 0
- D. Set max tokens to 1

**Answer:** A

**Explanation:** A higher temperature flattens the distribution so less likely tokens are sampled more often, which increases diversity and creativity but also the risk of errors.

### D2-009
*Multiple Choice | Medium*

**Question:** What does top-k do?

- A. Chooses the k best Regions
- B. Sets the number of training epochs
- C. Sets the number of chunks to retrieve only
- D. Limits sampling to the k most likely next tokens

**Answer:** D

**Explanation:** Top-k truncates the candidate list to the k highest-probability tokens before sampling. Smaller k makes output more conservative.

### D2-010
*Multiple Choice | Medium*

**Question:** What is the purpose of the max tokens (maximum length) parameter?

- A. Increases context window
- B. Caps the number of tokens the model may generate in a response
- C. Limits the number of users
- D. Controls data encryption

**Answer:** B

**Explanation:** It bounds response length, which controls cost and prevents runaway generation. If the cap is too low, the answer may be cut off.

### D2-011
*Multiple Choice | Medium*

**Question:** What is a stop sequence?

- A. A security protocol
- B. A billing alarm
- C. A string that, when generated, causes the model to stop producing further tokens
- D. A training-halt rule

**Answer:** C

**Explanation:** Stop sequences, such as a delimiter or a "Human:" marker, let applications end generation at a defined point.

### D2-012
*Multiple Choice | Easy*

**Question:** What is a hallucination in generative AI?

- A. A security breach
- B. The model produces fluent output that is incorrect, fabricated, or not grounded in facts or the provided source
- C. A GPU failure
- D. A slow response

**Answer:** B

**Explanation:** LLMs generate plausible text from patterns and may invent facts, citations, or details. Mitigations include RAG, grounding, guardrails, and human review.

### D2-013
*True/False | Medium*

**Question:** The same prompt sent to a generative model multiple times can produce different responses.

- A. True
- B. False

**Answer:** True

**Explanation:** Sampling introduces randomness, so outputs are nondeterministic unless temperature is set near zero. Even then, some variability may remain.

### D2-014
*Multiple Choice | Medium*

**Question:** In generative AI, what is a prompt?

- A. A model's training dataset
- B. A billing statement
- C. The input instruction or context given to the model to guide its output
- D. The final output of a model

**Answer:** C

**Explanation:** Prompts can include instructions, context, examples, and questions. Their quality strongly influences output quality.

### D2-015
*Multiple Choice | Medium*

**Question:** Which is a known limitation of foundation models?

- A. They have a knowledge cutoff, so they lack information about events after training unless supplemented
- B. They always produce correct results
- C. They cannot be used through APIs
- D. They can never process text

**Answer:** A

**Explanation:** Models only know what was in their training data. Techniques such as RAG supply current or private information at inference time.

### D2-016
*Multiple Choice | Medium*

**Question:** Which is a stage in the foundation model lifecycle?

- A. Deleting the dataset after training
- B. Defining the use case and selecting a model
- C. Disabling encryption
- D. Removing all logging

**Answer:** B

**Explanation:** Typical stages include data selection, model selection, pretraining, fine-tuning, evaluation, deployment, and feedback and monitoring.

### D2-017
*Multiple Choice | Medium*

**Question:** What is pretraining in the FM lifecycle?

- A. Testing the model with users
- B. Deploying the model to production
- C. Training on a few labeled examples for one task
- D. Training on very large amounts of broad, mostly unlabeled data to learn general representations

**Answer:** D

**Explanation:** Pretraining is self-supervised, such as predicting the next token. It gives the model general knowledge and language abilities, which can later be adapted.

### D2-018
*Multiple Choice | Medium*

**Question:** How does fine-tuning differ from pretraining?

- A. Fine-tuning uses far more data than pretraining
- B. Fine-tuning creates a model from random weights
- C. Fine-tuning only changes the user interface
- D. Fine-tuning adapts a pretrained model to a specific task or domain using a smaller, targeted dataset

**Answer:** D

**Explanation:** Fine-tuning updates a pretrained model's weights on task-specific data, which is much cheaper than training from scratch.

### D2-019
*Multiple Choice | Medium*

**Question:** Which customization approach generally has the lowest cost and effort?

- A. Continued pretraining
- B. Prompt engineering
- C. Pretraining a new model from scratch
- D. Fine-tuning with a large dataset

**Answer:** B

**Explanation:** Prompt engineering needs no training. It only changes the input to guide the model.

### D2-020
*Multiple Choice | Hard*

**Question:** Which ordering lists FM customization approaches from lowest to highest typical cost and effort?

- A. Fine-tuning, prompt engineering, pretraining from scratch, RAG
- B. Pretraining from scratch, fine-tuning, RAG, prompt engineering
- C. Prompt engineering, RAG, fine-tuning, continued pretraining, pretraining from scratch
- D. RAG, pretraining from scratch, prompt engineering, fine-tuning

**Answer:** C

**Explanation:** Prompt engineering is cheapest, then RAG (retrieval infrastructure), then fine-tuning (labeled data and training), then continued pretraining, then building a new model, which is the most expensive.

### D2-021
*True/False | Medium*

**Question:** Training a foundation model from scratch is generally quick and inexpensive for most organizations.

- A. True
- B. False

**Answer:** False

**Explanation:** Pretraining requires massive datasets, large GPU or accelerator clusters, and specialized expertise. Most organizations adopt existing FMs and customize them.

### D2-022
*Multiple Choice | Easy*

**Question:** Which is a common business use case for generative AI?

- A. Replacing network cables
- B. Raising CPU clock speed
- C. Summarizing long documents and drafting customer-support replies
- D. Formatting hard drives

**Answer:** C

**Explanation:** Text generation, summarization, chat assistants, code generation, image creation, and search enhancement are typical generative AI applications.

### D2-023
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO are challenges or disadvantages of generative AI? (Select TWO.)

- A. Inability to process any language
- B. Impossibility of API access
- C. Hallucinations
- D. Lower response speed than manual work
- E. Toxicity or inappropriate content

**Answer:** C, E

**Explanation:** Known challenges include hallucinations, toxicity, nondeterminism, interpretability issues, data privacy concerns, and regulatory or ethical risks.

### D2-024
*Multiple Choice | Medium*

**Question:** Which is an example of a business metric for evaluating a generative AI application?

- A. Number of tokens in the vocabulary
- B. GPU model name
- C. Layer count
- D. User satisfaction or conversion rate

**Answer:** D

**Explanation:** Business metrics tie the application to outcomes, such as user satisfaction, average revenue per user (ARPU), conversion rate, and efficiency gains, rather than only model-level scores.

### D2-025
*Multiple Choice | Medium*

**Question:** What does ARPU stand for, and what does it measure?

- A. Automated response per user, measuring chatbot volume
- B. Applied retrieval per update, measuring search speed
- C. Annual rate per upload, measuring storage
- D. Average revenue per user, measuring revenue generated per user

**Answer:** D

**Explanation:** ARPU shows the average revenue generated per user, and a generative feature such as personalized recommendations may be assessed by its effect on it.

### D2-026
*Multiple Choice | Medium*

**Question:** A support chatbot is intended to reduce agent workload. Which business metric best indicates efficiency gains?

- A. Context window size
- B. Temperature
- C. Reduction in average handling time or ticket deflection rate
- D. BLEU score

**Answer:** C

**Explanation:** Efficiency metrics such as handle time, tickets resolved by automation, and productivity gains show business impact.

### D2-027
*Multiple Choice | Medium*

**Question:** Which statement about Amazon Bedrock is accurate?

- A. You must provision and manage GPU servers yourself
- B. It can only be used on-premises
- C. It provides access to models from multiple providers through one API without managing infrastructure
- D. It only supports a single model

**Answer:** C

**Explanation:** Bedrock's serverless experience lets teams experiment with and switch between models, such as Amazon Nova and Titan, Anthropic Claude, Meta Llama, Mistral, Cohere, and Stability AI, using a unified API.

### D2-028
*Multiple Choice | Medium*

**Question:** What is Amazon Titan?

- A. A network appliance
- B. A virtual machine type
- C. An AWS Region
- D. A family of foundation models developed by Amazon and available in Bedrock, including text, embeddings, and image generation models

**Answer:** D

**Explanation:** Titan models cover text generation, text and multimodal embeddings, and image generation, and they are accessed through Amazon Bedrock.

### D2-029
*Multiple Choice | Medium*

**Question:** What is Amazon Nova?

- A. A database engine
- B. Amazon's family of foundation models available through Amazon Bedrock
- C. A storage class
- D. A VPC feature

**Answer:** B

**Explanation:** Amazon Nova is Amazon's FM family offered in Bedrock for text, multimodal understanding, and content generation, which gives builders more model choices on the same service.

### D2-030
*Multiple Choice | Medium*

**Question:** What is PartyRock?

- A. A GPU rental service
- B. An Amazon Bedrock Playground for building generative AI apps through a no-code interface, useful for learning and experimentation
- C. A tool for encrypting S3 objects
- D. A CI/CD service

**Answer:** B

**Explanation:** PartyRock lets people create and share small generative AI applications without code and without needing an AWS account for basic exploration.

### D2-031
*Multiple Choice | Easy*

**Question:** What is Amazon Q Business?

- A. A DNS service
- B. A generative AI assistant that can answer questions, summarize content, and complete tasks using an organization's enterprise data and systems
- C. A monitoring dashboard
- D. A data warehouse

**Answer:** B

**Explanation:** Amazon Q Business connects to company data sources and applies access controls so employees get relevant answers based on content they are authorized to see.

### D2-032
*Multiple Choice | Medium*

**Question:** What is Amazon Q Developer?

- A. A graphing library
- B. A hardware accelerator
- C. A tool for physical security
- D. A generative AI assistant that helps with coding, debugging, and AWS development tasks

**Answer:** D

**Explanation:** Q Developer provides code suggestions, explanations, transformations, and AWS guidance within IDEs and the console.

### D2-033
*Multiple Choice | Medium*

**Question:** What is the purpose of the Amazon Bedrock playgrounds?

- A. To archive logs
- B. To experiment with models and prompts and compare outputs in the console without writing code
- C. To manage billing
- D. To visualize network traffic

**Answer:** B

**Explanation:** Playgrounds provide chat, text, and image interfaces where users can test prompts and inference parameters before integrating with applications.

### D2-034
*Multiple Choice | Medium*

**Question:** How does Amazon Bedrock handle customer prompts and data with respect to training the underlying base models?

- A. Customer data is always used to improve base models
- B. Customer data is shared with all providers
- C. Customer data is published publicly
- D. Customer data is not used to train the base foundation models

**Answer:** D

**Explanation:** AWS states that Bedrock does not use customer prompts and completions to train the base models or share them with model providers. Customizations remain private to the customer.

### D2-035
*Multiple Choice | Medium*

**Question:** What is the difference between on-demand and Provisioned Throughput pricing in Amazon Bedrock?

- A. On-demand pay-per-use (typically per token) suits variable workloads, while Provisioned Throughput reserves capacity for consistent performance
- B. On-demand charges a fixed hourly rate regardless of use
- C. Provisioned Throughput is free
- D. There is no difference

**Answer:** A

**Explanation:** On-demand is flexible with no commitment, while Provisioned Throughput buys dedicated model units, which are required for custom models and steady high-volume workloads.

### D2-036
*Multiple Choice | Medium*

**Question:** How does SageMaker JumpStart generally differ from Amazon Bedrock for using foundation models?

- A. JumpStart is only for images
- B. They are identical
- C. Bedrock requires you to manage the GPU instances
- D. Bedrock offers serverless API access, while JumpStart deploys models to endpoints you configure and manage in your account

**Answer:** D

**Explanation:** Bedrock abstracts infrastructure. JumpStart gives more control over hosting, such as instance types and endpoint configuration, which is useful when you need that control or specific open models.

### D2-037
*Multiple Choice | Medium*

**Question:** What are AWS Trainium and AWS Inferentia?

- A. Network switches
- B. Database engines
- C. Purpose-built ML accelerators that provide cost-effective performance for training and inference respectively
- D. Security scanners

**Answer:** C

**Explanation:** Trainium targets training and Inferentia targets inference. Both aim to lower cost and raise performance for deep learning and generative AI workloads.

### D2-038
*Multiple Choice | Medium*

**Question:** Which is an advantage of using AWS for generative AI applications?

- A. Limited model choice
- B. Faster time to market, scalability, security and compliance features, and lower barrier to entry
- C. No security tooling
- D. Requires building models from scratch

**Answer:** B

**Explanation:** AWS provides managed services such as Bedrock and SageMaker, scalable infrastructure, and security controls, which lowers the cost and complexity of building generative AI.

### D2-039
*Multiple Choice | Easy*

**Question:** What does a vector database store and search?

- A. Only binary files
- B. Only relational rows with no indexes
- C. Embeddings (vectors) and supports similarity search over them
- D. Only plain text logs

**Answer:** C

**Explanation:** Vector stores index high-dimensional embeddings so applications can find semantically similar items quickly. This is essential for RAG.

### D2-040
*Multiple Choice | Medium*

**Question:** What does Amazon Bedrock Knowledge Bases do?

- A. Monitors network packets
- B. Manages DNS records
- C. Trains models from scratch
- D. Connects FMs to your data sources, handling ingestion, embedding, and retrieval to implement RAG with managed workflows

**Answer:** D

**Explanation:** Knowledge Bases ingests documents, chunks them, creates embeddings, stores them in a vector store, and retrieves relevant context for prompts.

### D2-041
*Multiple Choice | Medium*

**Question:** How does semantic search differ from keyword search?

- A. Semantic search only matches exact words
- B. Keyword search uses embeddings
- C. Semantic search matches meaning using embeddings, so it can find relevant content even without identical words
- D. They are identical

**Answer:** C

**Explanation:** Embedding-based search retrieves conceptually related passages, such as "car" and "automobile", while keyword search depends on exact term overlap.

### D2-042
*Multiple Choice | Medium*

**Question:** What is chunking in a RAG pipeline?

- A. Deleting duplicate files only
- B. Combining all documents into one file
- C. Splitting documents into smaller segments before embedding and indexing them
- D. Encrypting documents

**Answer:** C

**Explanation:** Chunking keeps passages within embedding model limits and improves retrieval precision. Chunk size and overlap affect answer quality.

### D2-043
*Multiple Choice | Medium*

**Question:** Which Amazon model type is commonly used to convert text into vectors for semantic search?

- A. A text-to-speech model
- B. A speech recognition model
- C. A text embeddings model such as Amazon Titan Text Embeddings
- D. An image classification model

**Answer:** C

**Explanation:** Embedding models convert text to vectors that capture meaning, and the vectors are stored in a vector database for retrieval.

### D2-044
*Multiple Choice | Medium*

**Question:** Which metric is commonly used to evaluate the quality of text summaries by measuring overlap with reference summaries?

- A. RMSE
- B. ROUGE
- C. AUC
- D. BLEU only

**Answer:** B

**Explanation:** ROUGE (Recall-Oriented Understudy for Gisting Evaluation) compares n-gram and sequence overlap between generated and reference summaries.

### D2-045
*Multiple Choice | Medium*

**Question:** Which metric is traditionally used to evaluate machine translation quality?

- A. ROUGE-L only
- B. Accuracy
- C. F1 for clustering
- D. BLEU

**Answer:** D

**Explanation:** BLEU (Bilingual Evaluation Understudy) measures n-gram precision against reference translations.

### D2-046
*Multiple Choice | Medium*

**Question:** What does BERTScore assess?

- A. Training speed
- B. Semantic similarity between generated and reference text using contextual embeddings
- C. Token cost
- D. Number of layers

**Answer:** B

**Explanation:** Unlike pure n-gram overlap, BERTScore uses embeddings to compare meaning, so paraphrases score well.

### D2-047
*Multiple Choice | Medium*

**Question:** What does perplexity indicate for a language model?

- A. How uncertain the model is when predicting text, where lower is generally better
- B. The GPU temperature
- C. The cost per request
- D. The number of users

**Answer:** A

**Explanation:** Perplexity is derived from the model's probability of held-out text. Lower values mean the model predicts the text better.

### D2-048
*Multiple Choice | Hard*

**Question:** A team evaluates a summarization model against human-written reference summaries. Which approach is most appropriate for an automated overlap-based score?

- A. AUC-ROC
- B. Silhouette score
- C. ROUGE
- D. RMSE

**Answer:** C

**Explanation:** ROUGE is designed for summarization evaluation. Because overlap metrics miss meaning, it is often paired with BERTScore or human review.

### D2-049
*Multiple Choice | Hard*

**Question:** Why might relying only on overlap metrics such as BLEU or ROUGE be insufficient for evaluating generative output?

- A. They can undervalue valid paraphrases and do not directly measure factuality, tone, or safety
- B. They cannot be calculated
- C. They only work on images
- D. They are too expensive

**Answer:** A

**Explanation:** N-gram overlap penalizes outputs that are correct but worded differently, and it cannot detect hallucinations. Human evaluation and semantic or LLM-based metrics complement them.

### D2-050
*True/False | Medium*

**Question:** Automatic metrics alone are always sufficient to judge the quality of generative AI outputs.

- A. True
- B. False

**Answer:** False

**Explanation:** Automatic metrics miss nuance such as helpfulness, tone, and factual accuracy. Human evaluation and task-specific tests remain important.

### D2-051
*Multiple Choice | Medium*

**Question:** What are benchmark datasets such as MMLU or GLUE used for?

- A. Training models from scratch
- B. Encrypting prompts
- C. Storing production logs
- D. Standardized evaluation of model capabilities, enabling comparison across models

**Answer:** A

**Explanation:** Benchmarks provide consistent tasks and scoring for comparing models on language understanding, reasoning, and knowledge.

### D2-052
*Multiple Choice | Medium*

**Question:** In Amazon Bedrock, how is on-demand inference for text generation typically billed?

- A. Per input and output token processed
- B. Per kilobyte stored
- C. Per GPU hour regardless of use
- D. Per prompt author

**Answer:** A

**Explanation:** Billing counts the tokens in the prompt and the generated response, often at different rates, so concise prompts and bounded outputs reduce cost.

### D2-053
*Multiple Choice | Medium*

**Question:** How does model size typically relate to latency and cost?

- A. Larger models are always faster and cheaper
- B. Larger models usually deliver more capability but with higher latency and cost, so the smallest model that meets requirements is often best
- C. Size has no effect
- D. Smaller models are always less accurate in every task

**Answer:** B

**Explanation:** Right-sizing the model for the task balances quality, latency, and spend. Smaller models are often adequate for classification or extraction.

### D2-054
*Multiple Choice | Medium*

**Question:** Which factors should be considered when selecting a foundation model?

- A. Only the model's name
- B. Modality, context window, cost, latency, language support, customization options, and licensing
- C. Only the provider's logo
- D. Only the number of letters in the model name

**Answer:** B

**Explanation:** Model selection should match task requirements and constraints such as quality, price, speed, compliance, and available customization.

### D2-055
*Multiple Choice | Medium*

**Question:** Why does AWS Region availability matter when choosing a model in Bedrock?

- A. It is irrelevant
- B. Models and features vary by Region, which can affect data residency, latency, and compliance
- C. It determines the model's temperature
- D. It changes the model's vocabulary

**Answer:** B

**Explanation:** Not every model is offered in every Region. Teams must pick Regions that satisfy residency requirements and feature needs.

### D2-056
*Multiple Choice | Hard*

**Question:** An application needs consistent, predictable throughput and low latency for a fine-tuned custom model in Amazon Bedrock. Which option is required?

- A. A public endpoint with no capacity
- B. Spot instances
- C. On-demand inference only
- D. Provisioned Throughput for the custom model

**Answer:** D

**Explanation:** Custom models in Bedrock are served with Provisioned Throughput, which reserves model units to guarantee capacity and performance.

### D2-057
*Multiple Choice | Medium*

**Question:** Which describes an advantage of open-weight models?

- A. Their weights are available, allowing greater customization and flexibility, subject to the license terms
- B. They are never usable commercially
- C. They are always more accurate
- D. They cannot be customized

**Answer:** A

**Explanation:** Open-weight models can be fine-tuned and self-hosted, but their licenses may include restrictions that must be reviewed.

### D2-058
*Multiple Choice | Medium*

**Question:** Which is an example of a multimodal generative AI task?

- A. Describing the contents of an uploaded image in text
- B. Sorting a list of numbers
- C. Compressing a file
- D. Running a SQL join

**Answer:** A

**Explanation:** A multimodal model accepts an image plus a text prompt and generates a textual description, which crosses modalities.

### D2-059
*Multiple Choice | Medium*

**Question:** Which type of model would be used to produce an image from a textual description?

- A. A text classification model
- B. A speech recognition model
- C. A clustering algorithm
- D. A text-to-image model such as a diffusion model

**Answer:** D

**Explanation:** Text-to-image FMs such as Amazon Titan Image Generator or Stability AI models generate images conditioned on prompts.

### D2-060
*Multiple Choice | Medium*

**Question:** Which use case best illustrates code generation with generative AI?

- A. Clustering customers
- B. Suggesting and completing functions from natural language comments in an IDE
- C. Compressing images
- D. Detecting fraud in transactions

**Answer:** B

**Explanation:** Assistants such as Amazon Q Developer generate code, tests, and explanations from natural language context.

### D2-061
*Multiple Choice | Medium*

**Question:** Which is a typical generative AI chatbot use case?

- A. Storing backups
- B. Providing conversational customer support that answers questions in natural language
- C. Reducing disk latency
- D. Configuring VPC routes

**Answer:** B

**Explanation:** LLM-based assistants handle open-ended questions and can be grounded in company knowledge through RAG.

### D2-062
*Multiple Choice | Medium*

**Question:** Which scenario fits summarization?

- A. Encrypting a contract
- B. Printing a contract
- C. Deleting a contract
- D. Converting a long contract into a short list of key obligations

**Answer:** D

**Explanation:** Summarization condenses long content into shorter text that preserves key information. It is a primary LLM use case.

### D2-063
*True/False | Medium*

**Question:** LLMs generate text by repeatedly predicting the next token given the tokens so far.

- A. True
- B. False

**Answer:** True

**Explanation:** Autoregressive LLMs compute a probability distribution over the next token, sample from it, append it, and repeat.

### D2-064
*True/False | Medium*

**Question:** Embeddings can only be created for text.

- A. True
- B. False

**Answer:** False

**Explanation:** Embeddings can represent images, audio, and other data, and multimodal embedding models place different modalities in the same vector space.

### D2-065
*True/False | Medium*

**Question:** A model with more parameters is always the best choice for every task.

- A. True
- B. False

**Answer:** False

**Explanation:** Larger models can be costlier and slower, and smaller or specialized models often meet requirements at lower cost.

### D2-066
*True/False | Easy*

**Question:** Amazon Bedrock is serverless, so customers do not need to manage the underlying infrastructure for foundation models.

- A. True
- B. False

**Answer:** True

**Explanation:** Bedrock handles provisioning and scaling so teams can call models through APIs.

### D2-067
*Multiple Choice | Medium*

**Question:** What is the latent space in generative models?

- A. A hardware cache
- B. A compressed representation space where data features are encoded in lower dimensions
- C. A security zone
- D. A table of customer records

**Answer:** B

**Explanation:** Latent representations capture essential features. Sampling or interpolating within the latent space enables generation of new items.

### D2-068
*Multiple Choice | Medium*

**Question:** Which training approach lets LLMs learn from unlabeled text by predicting the next or masked tokens?

- A. Self-supervised learning
- B. Reinforcement learning only
- C. Supervised learning with human labels
- D. Clustering

**Answer:** A

**Explanation:** Self-supervised learning creates its own training signal from raw data, such as predicting hidden or upcoming tokens, which lets pretraining use huge unlabeled corpora.

### D2-069
*Multiple Choice | Medium*

**Question:** What is the difference between training and inference?

- A. They are the same
- B. Training happens after deployment only
- C. Inference teaches the model new weights
- D. Training learns model parameters from data, while inference uses the trained model to generate predictions or outputs

**Answer:** D

**Explanation:** Training updates parameters, and inference runs the fixed model on new inputs. Cost, latency, and hardware needs differ between the two.

### D2-070
*Multiple Choice | Medium*

**Question:** What are instruction-tuned models?

- A. Models with no training
- B. Models fine-tuned on examples of instructions and desired responses so they follow user directions better
- C. Models that cannot chat
- D. Models that only classify images

**Answer:** B

**Explanation:** Instruction tuning aligns pretrained models to follow prompts, which makes them more useful in assistants.

### D2-071
*Multiple Choice | Medium*

**Question:** What happens when a prompt plus the expected response exceeds a model's context window?

- A. The model forgets the training data
- B. The input or output may be truncated or the request may fail, so applications must manage length
- C. The request is always cheaper
- D. The model automatically expands its window

**Answer:** B

**Explanation:** Context limits are hard limits. Developers use summarization, chunking, or retrieval to fit relevant content.

### D2-072
*Multiple Choice | Easy*

**Question:** Which statement best describes zero-shot prompting?

- A. Using no tokens
- B. Fine-tuning the model first
- C. Asking the model to perform a task without giving any examples
- D. Providing many examples in the prompt

**Answer:** C

**Explanation:** Zero-shot relies on the model's pretrained knowledge. Few-shot prompting adds examples to guide format and behavior.

### D2-073
*Multiple Choice | Medium*

**Question:** Which generative AI use case helps when real data is scarce or sensitive?

- A. Port scanning
- B. Disk defragmentation
- C. Synthetic data generation
- D. DNS resolution

**Answer:** C

**Explanation:** Generative models can create realistic synthetic records or images to augment training data, though quality and bias still need validation.

### D2-074
*Multiple Choice | Medium*

**Question:** Which AWS layer of the generative AI stack includes tools to build with FMs, such as Amazon Bedrock?

- A. None of these
- B. The middle layer: tools and services to build and scale generative AI applications with FMs
- C. Infrastructure layer only
- D. Application layer only

**Answer:** B

**Explanation:** AWS describes three layers: infrastructure (chips, GPUs), tools and services (Bedrock, SageMaker), and applications (Amazon Q and others).

### D2-075
*Multiple Choice | Medium*

**Question:** Which providers' models can be accessed through Amazon Bedrock (availability varies by Region)?

- A. Only Amazon models
- B. Only open-source models
- C. No third-party models
- D. Models from Amazon and several third-party providers such as Anthropic, Meta, Mistral AI, Cohere, and Stability AI

**Answer:** D

**Explanation:** Bedrock's marketplace-style choice lets customers evaluate and switch among providers through one API.

### D2-076
*Multiple Choice | Medium*

**Question:** Which capability is an example of using a foundation model for translation without building a dedicated translation model?

- A. Running a database index rebuild
- B. Compressing audio
- C. Prompting a multilingual LLM to translate text into another language
- D. Training a clustering model

**Answer:** C

**Explanation:** Multilingual FMs can translate via prompts. Dedicated services such as Amazon Translate remain an option for specialized, high-volume needs.

### D2-077
*Multiple Choice | Medium*

**Question:** What does "grounding" a model's response mean?

- A. Connecting the model to a physical wire
- B. Increasing temperature
- C. Turning off the model
- D. Anchoring responses to trusted source data, such as retrieved documents, to improve factual accuracy

**Answer:** D

**Explanation:** Grounding supplies verifiable context, typically via RAG, so answers reflect authoritative content and reduce hallucinations.

### D2-078
*Multiple Choice | Medium*

**Question:** What does the term "emergent abilities" refer to in large models?

- A. Capabilities such as reasoning or in-context learning that appear at larger scale without being explicitly trained for
- B. Billing anomalies
- C. Hardware failures
- D. Network latency

**Answer:** A

**Explanation:** Some abilities appear to arise as models scale, which helps explain why large FMs can perform tasks they were never directly trained on.

### D2-079
*Multiple Choice | Medium*

**Question:** Which factor makes foundation models adaptable?

- A. They only work for one task
- B. They cannot be prompted
- C. They require rewriting the architecture for each use
- D. Broad pretraining lets one model handle many tasks through prompting or light customization

**Answer:** D

**Explanation:** Pretraining on diverse data gives general capabilities, so organizations can reuse one model across summarization, extraction, Q&A, and more.

### D2-080
*Multiple Choice | Medium*

**Question:** Which is a drawback of relying solely on a general-purpose LLM for answers about a company's internal policies?

- A. It will always know the policies
- B. It has no language ability
- C. It likely lacks private, current information and may hallucinate unless grounded in company data
- D. It is too fast

**Answer:** C

**Explanation:** Base models are not trained on private documents. RAG or customization is needed to provide accurate organization-specific answers.

### D2-081
*Multiple Choice | Medium*

**Question:** Why might an organization choose a smaller, task-specific model rather than the largest available model?

- A. Larger models are unavailable
- B. It may meet quality needs with lower latency and cost
- C. Smaller models cannot be used in production
- D. Smaller models are always more secure in every way

**Answer:** B

**Explanation:** Model right-sizing reduces spend and speeds responses when the task, such as classification or extraction, doesn't need maximum capability.

### D2-082
*Multiple Choice | Easy*

**Question:** Which type of output can a text-to-speech service such as Amazon Polly generate?

- A. Spoken audio from text
- B. Images from text
- C. SQL queries
- D. Network diagrams

**Answer:** A

**Explanation:** Polly synthesizes natural-sounding speech from text. It is separate from generative text models but is often combined with them in voice assistants.

### D2-083
*Multiple Choice | Medium*

**Question:** Which statement about responsiveness as an advantage of generative AI is accurate?

- A. It makes decisions slower
- B. It limits output to one language
- C. It can generate content and answers quickly on demand, improving user experience and productivity
- D. It requires manual rewriting

**Answer:** C

**Explanation:** Generative AI offers fast, interactive generation for drafting, Q&A, and personalization at scale.

### D2-084
*Multiple Choice | Medium*

**Question:** What does the "temperature = 0" setting generally aim for?

- A. Maximum creativity
- B. Near-deterministic, repeatable output that selects the most likely tokens
- C. Unlimited output length
- D. Training from scratch

**Answer:** B

**Explanation:** At or near zero, the model strongly favors the highest-probability tokens, giving more consistent output for tasks like extraction or classification.

### D2-085
*Multiple Choice | Easy*

**Question:** Which AWS service offers a single API for accessing foundation models from multiple providers?

- A. Amazon Macie
- B. AWS Glue
- C. Amazon Bedrock
- D. Amazon Polly

**Answer:** C

**Explanation:** Amazon Bedrock provides serverless access to models from Amazon and other providers through one API. Polly is text-to-speech, Glue is data integration, and Macie discovers sensitive data in S3.

### D2-086
*True/False | Easy*

**Question:** A hallucination occurs when a generative model produces fluent text that is incorrect or not supported by facts or source material.

- A. True
- B. False

**Answer:** True

**Explanation:** Models generate plausible token sequences, not verified facts, so they can fabricate details. Grounding and verification reduce the risk.

### D2-087
*Multiple Choice | Easy*

**Question:** Which of the following is an example of generative AI output?

- A. A new product image created from a text description
- B. A fraud label for a transaction
- C. A cluster ID assigned to a customer
- D. A churn probability score for a customer

**Answer:** A

**Explanation:** Generative AI creates new content such as images, text, or audio. Scores, labels, and cluster assignments are outputs of predictive or discriminative models.

### D2-088
*True/False | Easy*

**Question:** Increasing the temperature parameter makes a model's output more deterministic.

- A. True
- B. False

**Answer:** False

**Explanation:** Higher temperature increases randomness and diversity. Lower temperature, near zero, makes output more deterministic.

### D2-089
*Multiple Choice | Hard*

**Question:** A model's answers are accurate but frequently end abruptly in the middle of a sentence. Which inference setting is the most likely cause?

- A. Top-k set too high
- B. A stop sequence that is too long
- C. A max tokens (maximum length) value that is too low
- D. Temperature set too high

**Answer:** C

**Explanation:** When the generated response reaches the max tokens limit, generation stops, even mid-sentence. Raising the limit, or asking for shorter answers, fixes the problem.

### D2-090
*Multiple Choice | Hard*

**Question:** Model X costs $3 per 1 million input tokens and $15 per 1 million output tokens. A workload uses 2 million input tokens and 1 million output tokens per month. What is the monthly cost with Model X?

- A. $21
- B. $45
- C. $18
- D. $9

**Answer:** A

**Explanation:** Input cost is 2 x $3 = $6 and output cost is 1 x $15 = $15, for a total of $21. Output tokens are usually priced higher than input tokens.

---

## Domain 3: Applications of Foundation Models

### D3-001
*Multiple Choice | Medium*

**Question:** Which set of factors is most relevant when selecting a pretrained foundation model for an application?

- A. The number of AWS Regions in the account
- B. The color scheme of the console
- C. Only the model's release date
- D. Modality, cost, latency, context window length, language support, customization options, and model size

**Answer:** D

**Explanation:** Selection should weigh task fit and constraints: input and output modality, price per token, response time, maximum context, languages, and whether the model can be fine-tuned or integrated with tools such as RAG.

### D3-002
*Multiple Choice | Medium*

**Question:** What is a key advantage of RAG compared with fine-tuning for keeping answers current?

- A. RAG eliminates the need for any data
- B. RAG changes the model's weights
- C. RAG removes all hallucinations
- D. Knowledge can be updated by changing the indexed documents, with no retraining, and sources can be cited

**Answer:** D

**Explanation:** Updating a vector store is far cheaper and faster than retraining. RAG also enables citations, although it does not eliminate hallucinations entirely.

### D3-003
*Multiple Choice | Medium*

**Question:** Which sequence correctly describes a basic RAG workflow at query time?

- A. Generate answer, retrieve documents, embed query
- B. Embed the user query, retrieve similar chunks from a vector store, augment the prompt with them, and generate the response
- C. Fine-tune model, deploy, retrieve
- D. Retrieve documents, embed the query, delete the prompt

**Answer:** B

**Explanation:** The query is converted to an embedding, similar chunks are fetched, the prompt is built from the question and retrieved context, and the FM generates a grounded answer.

### D3-004
*Multiple Choice | Medium*

**Question:** Which data source do Amazon Bedrock Knowledge Bases commonly ingest documents from?

- A. Amazon S3
- B. Amazon Route 53
- C. Amazon Polly
- D. AWS Shield

**Answer:** A

**Explanation:** Knowledge Bases can sync documents from S3 and other supported connectors. The service handles chunking, embedding, and indexing into a vector store.

### D3-005
*Multiple Choice | Medium*

**Question:** Which is a supported vector store for Amazon Bedrock Knowledge Bases?

- A. Amazon Aurora PostgreSQL with pgvector (among others, such as OpenSearch Serverless)
- B. Amazon SQS
- C. AWS Config
- D. Amazon CloudFront

**Answer:** A

**Explanation:** Supported stores include Amazon OpenSearch Serverless, Aurora PostgreSQL, and several third-party options. Bedrock can also create an OpenSearch Serverless collection for you.

### D3-006
*Multiple Choice | Medium*

**Question:** Which Bedrock capability queries a knowledge base and generates a response with citations in a single managed call?

- A. CreateGuardrail
- B. RetrieveAndGenerate
- C. ListFoundationModels
- D. DeleteModel

**Answer:** B

**Explanation:** RetrieveAndGenerate retrieves relevant chunks, builds the augmented prompt, calls the model, and returns the answer with source attributions. The Retrieve API returns only the chunks.

### D3-007
*Multiple Choice | Hard*

**Question:** A RAG application returns vague answers. Investigation shows the document chunks are very large and contain many unrelated topics. What is the most likely improvement?

- A. Increase the temperature
- B. Use a smaller context window
- C. Use smaller, more focused chunks (with suitable overlap) so retrieval is more precise
- D. Remove the vector store

**Answer:** C

**Explanation:** Oversized chunks dilute relevance, while too-small chunks lose context. Tuning chunk size, overlap, or chunking strategy such as hierarchical or semantic chunking improves retrieval quality.

### D3-008
*Multiple Choice | Medium*

**Question:** Why would a team add metadata filtering to knowledge base retrieval?

- A. To change the tokenizer
- B. To narrow retrieval to documents matching attributes such as department, date, or product, improving relevance and access scoping
- C. To disable embeddings
- D. To increase the model size

**Answer:** B

**Explanation:** Metadata filters restrict which chunks are considered, so answers come from the right subset of content.

### D3-009
*Multiple Choice | Hard*

**Question:** What is hybrid search in a RAG system?

- A. Searching in two Regions at once
- B. Using two different models for generation
- C. Searching only images
- D. Combining semantic (vector) search with keyword search to improve retrieval coverage

**Answer:** D

**Explanation:** Hybrid search blends meaning-based retrieval, which is good for paraphrases, with lexical matching, which is good for exact terms and identifiers.

### D3-010
*Multiple Choice | Hard*

**Question:** What does a reranking model do in a RAG pipeline?

- A. Encrypts the index
- B. Compresses embeddings
- C. Generates the final answer
- D. Reorders the retrieved candidates by relevance to the query so the best passages go into the prompt

**Answer:** D

**Explanation:** Reranking applies a more precise relevance model to initially retrieved results, improving the quality of context that is passed to the FM.

### D3-011
*Multiple Choice | Medium*

**Question:** What are Amazon Bedrock Agents?

- A. A capability that lets an FM plan and execute multistep tasks by calling APIs and querying knowledge bases
- B. Antivirus agents
- C. Hardware monitoring agents
- D. DNS resolvers

**Answer:** A

**Explanation:** Agents break down requests, decide which actions to take, invoke company APIs through action groups (often AWS Lambda), and use knowledge bases to complete tasks.

### D3-012
*Multiple Choice | Medium*

**Question:** How can an agent in Amazon Bedrock access private company knowledge?

- A. By being associated with a knowledge base for retrieval
- B. By editing the console theme
- C. By training on the internet
- D. By disabling the model

**Answer:** A

**Explanation:** Agents can query associated knowledge bases to ground their reasoning in company data, in addition to calling APIs.

### D3-013
*Multiple Choice | Medium*

**Question:** What are Amazon Bedrock Guardrails?

- A. Network ACLs
- B. A model training tool
- C. Configurable safeguards that filter harmful content, deny topics, redact sensitive information, and check grounding in model inputs and outputs
- D. Physical security cameras

**Answer:** C

**Explanation:** Guardrails provide content filters, denied topics, word filters, sensitive information filters (PII), and contextual grounding checks. They work across models and can also be applied independently via the ApplyGuardrail API.

### D3-014
*Multiple Choice | Medium*

**Question:** What does a contextual grounding check in Guardrails evaluate?

- A. The model's training date
- B. Whether the response is grounded in the supplied source and relevant to the user's query, helping to detect hallucinations
- C. The user's IP address
- D. The GPU's temperature

**Answer:** B

**Explanation:** Grounding and relevance thresholds flag responses that are unsupported by the reference content or that stray from the question.

### D3-015
*Multiple Choice | Medium*

**Question:** A company wants its chatbot to refuse to give investment advice. Which Guardrails feature is the best fit?

- A. Word filters only
- B. Temperature
- C. Denied topics
- D. Sensitive information filters

**Answer:** C

**Explanation:** Denied topics let you define subjects, with descriptions and examples, that the application must not discuss, and the guardrail blocks matching inputs or outputs.

### D3-016
*Multiple Choice | Medium*

**Question:** Which statement about Amazon Bedrock Guardrails is accurate?

- A. They only work with Amazon Titan models
- B. They only filter user inputs
- C. They can evaluate both user inputs and model responses and be applied to different models
- D. They cannot detect PII

**Answer:** C

**Explanation:** Guardrails run on prompts and completions and can be attached to Bedrock model invocations or used on text from any source via ApplyGuardrail.

### D3-017
*Multiple Choice | Easy*

**Question:** What is prompt engineering?

- A. Writing network policies
- B. Building servers for models
- C. Training a model from scratch
- D. Designing and refining inputs to elicit desired outputs from a foundation model

**Answer:** D

**Explanation:** Prompt engineering shapes instructions, context, examples, and format to improve output quality without changing model weights.

### D3-018
*Multiple Choice | Medium*

**Question:** Which elements are commonly included in an effective prompt?

- A. Only a random seed
- B. Clear instructions, relevant context, the input data, and an output format indicator
- C. Only the user's name
- D. A GPU specification

**Answer:** B

**Explanation:** Well-structured prompts state the task, supply context and data, specify constraints, and indicate how the answer should be formatted.

### D3-019
*Multiple Choice | Medium*

**Question:** What is few-shot prompting?

- A. Fine-tuning with few GPUs
- B. Including a small number of input-output examples in the prompt to demonstrate the desired behavior
- C. Using few tokens
- D. Giving no examples

**Answer:** B

**Explanation:** Few-shot examples help the model infer the pattern, format, and tone to follow. This is a form of in-context learning.

### D3-020
*Multiple Choice | Medium*

**Question:** What is chain-of-thought (CoT) prompting?

- A. Chaining API calls
- B. Encouraging the model to reason step by step before giving a final answer
- C. Using blockchain for prompts
- D. Linking multiple models in a pipeline

**Answer:** B

**Explanation:** Asking for intermediate reasoning improves performance on multi-step problems such as math, logic, and planning.

### D3-021
*Multiple Choice | Medium*

**Question:** What is single-shot (one-shot) prompting?

- A. Providing no examples
- B. Providing the task to multiple models
- C. Providing exactly one example of the desired input and output in the prompt
- D. Sending one token only

**Answer:** C

**Explanation:** One-shot prompting offers a single demonstration, which sits between zero-shot (none) and few-shot (several).

### D3-022
*Multiple Choice | Medium*

**Question:** What is negative prompting commonly used for, for example in image generation?

- A. Making the model slower
- B. Specifying what the model should avoid including in the output
- C. Reducing resolution only
- D. Increasing the price

**Answer:** B

**Explanation:** Negative prompts state unwanted elements or styles, such as "blurry" or "text watermark", to steer the output away from them.

### D3-023
*Multiple Choice | Medium*

**Question:** What is a prompt template?

- A. A model checkpoint
- B. A reusable prompt structure with placeholders that are filled with variable content at runtime
- C. A fixed output
- D. A dataset schema

**Answer:** B

**Explanation:** Templates standardize instructions and context across requests, which promotes consistency and easier testing and versioning.

### D3-024
*Multiple Choice | Medium*

**Question:** What is the purpose of assigning a role or persona in a prompt, such as "You are a helpful financial analyst"?

- A. It sets context for tone, perspective, and expertise to shape the response
- B. It encrypts the response
- C. It lowers token cost
- D. It changes the model weights

**Answer:** A

**Explanation:** Role prompting guides style and focus. It does not add knowledge the model lacks.

### D3-025
*Multiple Choice | Medium*

**Question:** Which prompt practice helps get machine-readable output?

- A. Using random words
- B. Explicitly specifying the output format, such as valid JSON with named fields
- C. Asking for "something nice"
- D. Leaving out all instructions

**Answer:** B

**Explanation:** Clear format instructions, often with an example schema, improve consistency and make responses easy to parse downstream.

### D3-026
*Multiple Choice | Medium*

**Question:** Why use delimiters or clear structure, such as XML-style tags, to separate instructions from user-provided content in a prompt?

- A. To help the model distinguish instructions from data and reduce the risk of prompt injection
- B. To change billing
- C. To reduce the vocabulary
- D. To increase the temperature

**Answer:** A

**Explanation:** Separating trusted instructions from untrusted input improves clarity and makes it harder for injected text to override the instructions.

### D3-027
*Multiple Choice | Medium*

**Question:** Which is a prompt engineering best practice?

- A. Never test prompts
- B. Use vague, short prompts
- C. Avoid specifying format
- D. Be specific and clear, provide context and examples, and iterate based on results

**Answer:** D

**Explanation:** Specificity, context, examples, and iterative refinement are core practices for reliable results.

### D3-028
*Multiple Choice | Hard*

**Question:** A team needs a model to classify customer reviews as positive, negative, or neutral in a company-specific way. They add three labeled example reviews to each prompt. Which technique is this?

- A. Continued pretraining
- B. Reinforcement learning
- C. Zero-shot prompting
- D. Few-shot prompting

**Answer:** D

**Explanation:** Including a handful of labeled examples in the prompt demonstrates the desired classification behavior without any training.

### D3-029
*Multiple Choice | Medium*

**Question:** What is a prompt injection attack?

- A. Training on bad data
- B. Injecting SQL into a database
- C. Crafting input that manipulates the model into ignoring its instructions or performing unintended actions
- D. Overloading a server with requests

**Answer:** C

**Explanation:** Attackers embed instructions in user input or retrieved content to override system prompts or exfiltrate data. Defenses are layered.

### D3-030
*Multiple Choice | Medium*

**Question:** What does "jailbreaking" an LLM refer to?

- A. Backing up a model
- B. Scaling a model
- C. Crafting prompts to bypass the model's safety restrictions and make it produce disallowed content
- D. Physically modifying hardware

**Answer:** C

**Explanation:** Jailbreaks use role play, obfuscation, or multi-step tricks to circumvent safety alignment.

### D3-031
*Multiple Choice | Medium*

**Question:** What is prompt leaking?

- A. Losing network packets
- B. A billing mistake
- C. Getting the model to reveal hidden system prompts or confidential instructions
- D. Over-training

**Answer:** C

**Explanation:** Attackers try to extract system prompts, which may contain proprietary logic or secrets. Sensitive data should not be placed in system prompts.

### D3-032
*Multiple Choice | Hard*

**Question:** Which combination best reduces prompt injection risk in a production application?

- A. Input and output filtering with Guardrails, clear separation of instructions from data, and least-privilege access for any tools or actions the model can invoke
- B. Hiding the system prompt and doing nothing else
- C. Trusting all user input
- D. Granting the model full administrative permissions

**Answer:** A

**Explanation:** Defense in depth is required. Guardrails and validation filter content, structured prompts limit confusion, and least privilege limits impact if the model is manipulated.

### D3-033
*True/False | Medium*

**Question:** Providing examples in a prompt can improve the consistency of the output format.

- A. True
- B. False

**Answer:** True

**Explanation:** Examples demonstrate the expected structure and style. This is why few-shot prompting is widely used.

### D3-034
*Multiple Choice | Medium*

**Question:** Which Bedrock feature helps teams create, version, and manage prompts for reuse across applications?

- A. AWS Artifact
- B. Amazon Route 53
- C. Amazon Bedrock Prompt Management
- D. Amazon Macie

**Answer:** C

**Explanation:** Prompt Management lets teams build, test, version, and share prompts, which supports governance and consistent behavior.

### D3-035
*Multiple Choice | Medium*

**Question:** What is Amazon Bedrock Flows used for?

- A. Monitoring VPC flow logs
- B. Visually building generative AI workflows that link prompts, models, knowledge bases, and other components
- C. Compressing prompts
- D. Storing embeddings

**Answer:** B

**Explanation:** Flows provides a visual builder to orchestrate multistep generative AI workflows without extensive code.

### D3-036
*Multiple Choice | Medium*

**Question:** What is the Amazon Bedrock Converse API?

- A. A network API
- B. A unified API for multi-turn conversations that works consistently across supported models
- C. A model training API only
- D. A billing API

**Answer:** B

**Explanation:** Converse provides a consistent message format, system prompts, and tool use across models, which simplifies switching models.

### D3-037
*Multiple Choice | Medium*

**Question:** Which option returns model output incrementally as it is generated, improving perceived latency in chat applications?

- A. Response streaming (for example, InvokeModelWithResponseStream or ConverseStream)
- B. Model distillation
- C. Provisioned Throughput
- D. Batch inference

**Answer:** A

**Explanation:** Streaming sends tokens as they are produced, so users see text sooner rather than waiting for the full response.

### D3-038
*Multiple Choice | Medium*

**Question:** A company must process millions of documents overnight with no real-time requirement and wants to lower inference cost. Which Bedrock option fits?

- A. Real-time on-demand calls only
- B. Batch inference
- C. Streaming
- D. Interactive playground

**Answer:** B

**Explanation:** Batch inference processes large sets of prompts asynchronously, typically at lower cost than on-demand, with results written to S3.

### D3-039
*Multiple Choice | Medium*

**Question:** What is the benefit of cross-Region inference in Amazon Bedrock?

- A. It trains models faster
- B. It deletes old models
- C. It routes requests across multiple Regions to improve throughput and resilience during traffic spikes
- D. It removes the need for IAM

**Answer:** C

**Explanation:** Inference profiles distribute traffic to other Regions in a defined geography, which helps manage bursts. Teams must still confirm that data residency requirements are met.

### D3-040
*Multiple Choice | Medium*

**Question:** What does prompt caching in Bedrock do?

- A. Encrypts responses
- B. Stores model weights offline
- C. Increases temperature
- D. Caches frequently reused prompt prefixes to reduce latency and cost on repeated context

**Answer:** D

**Explanation:** When large parts of a prompt, such as long documents or instructions, repeat across requests, caching avoids reprocessing them each time.

### D3-041
*Multiple Choice | Medium*

**Question:** How is training data typically provided for fine-tuning a model in Amazon Bedrock?

- A. As emails
- B. As spreadsheets in a DynamoDB stream
- C. As images in a Route 53 zone
- D. As labeled prompt-completion examples in JSON Lines format stored in Amazon S3

**Answer:** D

**Explanation:** Fine-tuning uses labeled examples that show desired outputs for given inputs, stored in S3 with appropriate permissions.

### D3-042
*Multiple Choice | Medium*

**Question:** What is continued pretraining?

- A. Further training a pretrained model on unlabeled domain-specific data to improve its domain knowledge
- B. Adding examples to prompts
- C. Using a prompt library
- D. Fine-tuning with labeled prompts only

**Answer:** A

**Explanation:** Continued pretraining uses large amounts of unlabeled text, such as industry documents, to adapt the model to a domain before or instead of task-specific fine-tuning.

### D3-043
*Multiple Choice | Medium*

**Question:** What is instruction tuning?

- A. Tuning hardware
- B. Adjusting the temperature
- C. Fine-tuning a model on examples of instructions paired with desired responses to improve how it follows directions
- D. Writing instructions for staff

**Answer:** C

**Explanation:** It improves instruction-following and is a common way to make base models more useful in assistants.

### D3-044
*Multiple Choice | Medium*

**Question:** Which statement best describes transfer learning when customizing a foundation model?

- A. Reusing knowledge from a model trained on a large task as the starting point for a related task
- B. Transferring a bucket
- C. Moving data between Regions
- D. Copying prompts

**Answer:** A

**Explanation:** Starting from a pretrained model reduces data and compute needs. Fine-tuning an FM is an example.

### D3-045
*Multiple Choice | Hard*

**Question:** A company needs the model to consistently adopt a specific writing style and domain terminology across all outputs, and it has thousands of high-quality labeled examples. Which approach is most suitable?

- A. Prompt engineering with zero-shot only
- B. RAG only
- C. Increasing temperature
- D. Fine-tuning the model on the labeled examples

**Answer:** D

**Explanation:** When the goal is consistent behavior or style, rather than fresh knowledge, fine-tuning on curated examples is effective.

### D3-046
*Multiple Choice | Medium*

**Question:** Which factor is most important when preparing data for fine-tuning?

- A. The number of columns in a spreadsheet
- B. The file's creation date
- C. High-quality, representative, correctly labeled, and properly governed examples
- D. The color of the files

**Answer:** C

**Explanation:** Fine-tuned behavior reflects the data. Poor, biased, or noisy examples degrade results, and sensitive content needs governance.

### D3-047
*Multiple Choice | Medium*

**Question:** What is catastrophic forgetting in fine-tuning?

- A. A security incident
- B. The model losing previously learned general capabilities after being fine-tuned too aggressively on a narrow dataset
- C. Losing the S3 bucket
- D. Deleting logs

**Answer:** B

**Explanation:** Over-specialization can degrade general knowledge. Remedies include lower learning rates, fewer epochs, and mixing in broader data.

### D3-048
*Multiple Choice | Medium*

**Question:** What is model distillation?

- A. Compressing files
- B. Training a smaller student model to mimic a larger teacher model's outputs to reduce cost and latency
- C. Splitting datasets
- D. Deleting unused models

**Answer:** B

**Explanation:** Distillation transfers capability from a large model to a smaller one, which preserves much of the quality for specific tasks at lower inference cost.

### D3-049
*Multiple Choice | Medium*

**Question:** What does Amazon Bedrock Custom Model Import allow?

- A. Importing IAM users
- B. Importing customized model weights of supported architectures into Bedrock for serverless use
- C. Importing VPCs
- D. Importing S3 buckets

**Answer:** B

**Explanation:** Teams that fine-tuned a supported open architecture elsewhere can bring the model into Bedrock and invoke it through the Bedrock APIs.

### D3-050
*Multiple Choice | Medium*

**Question:** What must typically be purchased to run a customized (fine-tuned) model in Amazon Bedrock?

- A. Provisioned Throughput
- B. A Route 53 hosted zone
- C. A Direct Connect line
- D. Spot capacity

**Answer:** A

**Explanation:** Custom models are served through Provisioned Throughput, which reserves dedicated capacity.

### D3-051
*Multiple Choice | Medium*

**Question:** What is domain adaptation fine-tuning?

- A. Moving accounts
- B. Registering a website
- C. Adapting a pretrained model to a specific industry or field, such as legal or medical, using domain data
- D. Changing a DNS domain

**Answer:** C

**Explanation:** Domain adaptation tailors terminology and knowledge to a field, improving relevance on domain-specific tasks.

### D3-052
*True/False | Medium*

**Question:** Fine-tuning a model for instruction following typically uses labeled prompt-and-response examples.

- A. True
- B. False

**Answer:** True

**Explanation:** Supervised fine-tuning needs paired inputs and desired outputs to teach the model the target behavior.

### D3-053
*Multiple Choice | Medium*

**Question:** What is the purpose of parameter-efficient fine-tuning (PEFT) techniques such as LoRA?

- A. To adapt a model by training only a small number of added parameters, reducing compute and memory needs
- B. To delete weights
- C. To increase model size
- D. To disable GPUs

**Answer:** A

**Explanation:** PEFT methods update a small set of parameters or adapters while keeping most weights frozen, which makes fine-tuning cheaper and faster.

### D3-054
*Multiple Choice | Medium*

**Question:** Which are typical hyperparameters adjusted in fine-tuning jobs?

- A. Bucket ACLs
- B. DNS TTL
- C. Region name, VPC ID, and bucket name
- D. Epochs, learning rate, and batch size

**Answer:** D

**Explanation:** These settings control training duration, step size, and how many examples are processed per update. Poor choices can cause under- or overfitting.

### D3-055
*Multiple Choice | Medium*

**Question:** What evaluation approaches does Amazon Bedrock Model Evaluation support?

- A. Automatic evaluation with metrics, human evaluation workflows, and LLM-as-a-judge evaluation
- B. Only hardware benchmarks
- C. Only billing analysis
- D. None

**Answer:** A

**Explanation:** Teams can compare models or prompts using built-in metrics such as accuracy, robustness, and toxicity, human reviewers, or a judge model.

### D3-056
*Multiple Choice | Medium*

**Question:** Why include human evaluation when assessing generative AI outputs?

- A. It removes all bias
- B. It is cheaper than automation
- C. It captures subjective qualities such as helpfulness, tone, creativity, and nuance that automated metrics may miss
- D. It is required by AWS billing

**Answer:** C

**Explanation:** Human judgments complement automated scores, especially for style, safety, and usefulness.

### D3-057
*Multiple Choice | Medium*

**Question:** What is the LLM-as-a-judge evaluation approach?

- A. Using a capable model to score or compare outputs of other models against criteria like correctness or helpfulness
- B. Using a legal database
- C. Training a judge model from scratch only
- D. Hiring a lawyer

**Answer:** A

**Explanation:** Judge models scale evaluation cheaply and quickly. Calibrating them against human ratings is still advisable.

### D3-058
*Multiple Choice | Medium*

**Question:** Which metric measures overlap of n-grams between generated and reference summaries?

- A. Silhouette
- B. AUC
- C. ROUGE
- D. BERTScore

**Answer:** C

**Explanation:** ROUGE-N counts overlapping n-grams, and ROUGE-L uses the longest common subsequence. It is common in summarization evaluation.

### D3-059
*Multiple Choice | Medium*

**Question:** Which metric uses contextual embeddings to evaluate semantic similarity between generated and reference text?

- A. Accuracy
- B. BLEU
- C. ROUGE-1
- D. BERTScore

**Answer:** D

**Explanation:** BERTScore compares token embeddings, so it rewards meaning-preserving paraphrases that n-gram metrics might penalize.

### D3-060
*Multiple Choice | Hard*

**Question:** How can a company determine whether a foundation model application effectively meets business objectives?

- A. Define success criteria such as productivity gains, user engagement, and task completion, and measure them with the application
- B. Check only the model's parameter count
- C. Check only the server color
- D. Rely solely on perplexity

**Answer:** A

**Explanation:** Model-level scores are not enough. Business outcomes such as time saved, resolution rate, and user satisfaction demonstrate real value.

### D3-061
*Multiple Choice | Hard*

**Question:** Which set of measures is appropriate for evaluating a RAG application?

- A. Retrieval relevance, answer faithfulness (groundedness), and answer relevance to the question
- B. Only network latency
- C. Only storage cost
- D. Only GPU utilization

**Answer:** A

**Explanation:** RAG quality depends on retrieving the right context and on the model staying faithful to it. Bedrock RAG evaluation checks both.

### D3-062
*Multiple Choice | Medium*

**Question:** A team wants to compare two prompts in production using real users to see which produces better outcomes. Which method fits?

- A. A/B testing
- B. Fine-tuning
- C. Data labeling
- D. Hyperparameter tuning

**Answer:** A

**Explanation:** A/B testing splits traffic between variants and compares outcome metrics, which provides real-world evidence of which performs better.

### D3-063
*Multiple Choice | Medium*

**Question:** Which generative AI application is an example of converting natural language into database queries?

- A. Disk formatting
- B. Speech synthesis
- C. Image captioning
- D. Text-to-SQL, where an FM generates SQL from a question and a schema description

**Answer:** D

**Explanation:** With schema context in the prompt, FMs can draft SQL queries. Results should be validated and executed with least-privilege access.

### D3-064
*Multiple Choice | Medium*

**Question:** How can embeddings be used for recommendations or similar-item search?

- A. By finding items whose vectors are closest to a query or user vector
- B. By compressing videos
- C. By changing IAM roles
- D. By storing credentials

**Answer:** A

**Explanation:** Nearest-neighbor search in embedding space retrieves semantically similar products, articles, or images.

### D3-065
*Multiple Choice | Medium*

**Question:** How can a chatbot built on a stateless FM API remember earlier turns of a conversation?

- A. By including relevant conversation history in the prompt (or using a managed memory feature) on each request
- B. By restarting the model
- C. The model automatically remembers all sessions forever
- D. By enabling a firewall

**Answer:** A

**Explanation:** FM calls are independent. Applications must supply prior messages or summaries, within context window limits.

### D3-066
*Multiple Choice | Medium*

**Question:** Amazon Q Business respects existing access permissions from connected data sources. Why is this important?

- A. It reduces storage
- B. It makes responses longer
- C. Users receive answers based only on content they are authorized to access
- D. It speeds up GPUs

**Answer:** C

**Explanation:** Honoring source permissions prevents oversharing of confidential information through the assistant.

### D3-067
*Multiple Choice | Medium*

**Question:** A company wants to automatically block or mask toxic content and PII in model responses across applications. Which service capability is most appropriate?

- A. Amazon Route 53
- B. AWS Direct Connect
- C. AWS Shield
- D. Amazon Bedrock Guardrails

**Answer:** D

**Explanation:** Guardrails apply content filters and sensitive-information filters, such as blocking or masking PII, consistently to prompts and responses.

### D3-068
*Multiple Choice | Medium*

**Question:** Which prompt technique helps extract structured fields, such as invoice number and date, from unstructured text?

- A. Instructing the model to return a specified JSON schema and providing examples
- B. Setting temperature to the maximum
- C. Asking for a poem
- D. Using an empty prompt

**Answer:** A

**Explanation:** Defining the expected schema and showing examples, with low temperature, yields reliable structured extraction.

### D3-069
*Multiple Choice | Hard*

**Question:** A travel company wants an assistant that can check flight availability and create bookings by calling its internal APIs. Which Bedrock capability fits best?

- A. Model evaluation
- B. Amazon Bedrock Agents with action groups
- C. Amazon Polly
- D. Guardrails

**Answer:** B

**Explanation:** Agents plan multistep tasks and invoke APIs through action groups, which makes them ideal for task-completing assistants.

### D3-070
*Multiple Choice | Hard*

**Question:** A firm wants employees to ask questions answered from 20,000 internal PDFs that are updated weekly, with source citations. Which solution best fits?

- A. Training a model from scratch
- B. A prompt with no context
- C. Fine-tuning monthly with no retrieval
- D. Amazon Bedrock Knowledge Bases (RAG) with periodic data sync

**Answer:** D

**Explanation:** RAG with a managed knowledge base provides current, cited answers without retraining, and re-syncing keeps the index fresh.

### D3-071
*Multiple Choice | Hard*

**Question:** A brand needs all generated copy to match a distinctive voice, and the team wants the lowest-effort first attempt before investing in training. What should they try first?

- A. Pretraining a new model
- B. Fine-tuning immediately
- C. Prompt engineering with a style guide and few-shot examples
- D. Building a custom GPU cluster

**Answer:** C

**Explanation:** Prompting is the cheapest, fastest experiment. Only if it falls short should the team move up to fine-tuning.

### D3-072
*Multiple Choice | Hard*

**Question:** A legal-summary app must prevent personal data in documents from appearing in outputs. Which feature should be configured?

- A. Guardrails sensitive information filters to detect and mask or block PII
- B. Higher top-p
- C. More epochs
- D. A larger context window

**Answer:** A

**Explanation:** PII filters can redact or block entities such as names, SSNs, and emails in prompts or responses.

### D3-073
*Multiple Choice | Hard*

**Question:** A customer-facing chat application needs fast perceived responses and low cost per request. Which combination is most appropriate?

- A. Largest model, maximum tokens, no streaming
- B. A right-sized smaller model, concise prompts, and response streaming
- C. Batch inference only
- D. No guardrails

**Answer:** B

**Explanation:** Smaller models and short prompts reduce latency and tokens, and streaming improves perceived responsiveness.

### D3-074
*Multiple Choice | Hard*

**Question:** An analytics team will summarize 500,000 archived support tickets over a weekend with no user waiting. Which approach minimizes cost?

- A. Bedrock batch inference writing results to S3
- B. Real-time on-demand calls from a web app
- C. Provisioned Throughput all year
- D. Interactive playground sessions

**Answer:** A

**Explanation:** Asynchronous, non-interactive workloads suit batch inference, which is typically cheaper per token.

### D3-075
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO components are essential parts of a RAG architecture? (Select TWO.)

- A. A vector store (or other retrievable index)
- B. A clustering algorithm
- C. A Spot Fleet
- D. A generative adversarial network
- E. An embedding model

**Answer:** A, E

**Explanation:** RAG needs embeddings to represent content and queries, plus an index to retrieve relevant chunks. The generator FM then uses them.

### D3-076
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO approaches help reduce hallucinations? (Select TWO.)

- A. Using contextual grounding checks in Guardrails
- B. Grounding responses with retrieved source documents (RAG)
- C. Removing all instructions from the prompt
- D. Hiding source citations
- E. Raising the temperature

**Answer:** A, B

**Explanation:** Supplying authoritative context and verifying grounding both reduce unsupported claims. Higher temperature and vague prompts tend to increase errors.

### D3-077
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO are prompt engineering techniques? (Select TWO.)

- A. Principal component analysis
- B. Gradient boosting
- C. Backpropagation
- D. Chain-of-thought prompting
- E. Few-shot prompting

**Answer:** D, E

**Explanation:** Few-shot and chain-of-thought are prompting methods. The other options are training or ML algorithms.

### D3-078
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO capabilities can an agent for Amazon Bedrock use to complete a user's request? (Select TWO.)

- A. Invoking APIs through action groups
- B. Resizing EC2 instances without permissions
- C. Querying an associated knowledge base
- D. Rewriting IAM policies on its own
- E. Changing billing plans

**Answer:** A, C

**Explanation:** Agents orchestrate API calls and retrieval within the permissions and definitions they are given. They cannot exceed their configured scope.

### D3-079
*True/False | Medium*

**Question:** RAG permanently changes the weights of the foundation model.

- A. True
- B. False

**Answer:** False

**Explanation:** RAG supplies retrieved context in the prompt at inference time. It does not alter model weights, which is why knowledge updates need no retraining.

### D3-080
*True/False | Medium*

**Question:** Amazon Bedrock Knowledge Bases can return source attributions (citations) for generated answers.

- A. True
- B. False

**Answer:** True

**Explanation:** Responses include references to the retrieved chunks and source documents, which supports verification and trust.

### D3-081
*True/False | Medium*

**Question:** Amazon Bedrock Guardrails evaluate only the model's outputs and never the user's inputs.

- A. True
- B. False

**Answer:** False

**Explanation:** Guardrails can screen both user inputs and model outputs, blocking harmful prompts and filtering responses.

### D3-082
*True/False | Medium*

**Question:** A high temperature setting is generally recommended for deterministic data extraction tasks.

- A. True
- B. False

**Answer:** False

**Explanation:** Extraction needs consistent, accurate output, so low temperature is recommended. High temperature adds randomness.

### D3-083
*Multiple Choice | Medium*

**Question:** What is in-context learning?

- A. The model's ability to learn a task from instructions or examples supplied in the prompt, without weight updates
- B. Training on private data in S3
- C. Retraining overnight
- D. Updating the weights during inference

**Answer:** A

**Explanation:** Few-shot examples and instructions let a frozen model adapt its behavior within a single request.

### D3-084
*Multiple Choice | Medium*

**Question:** Which approach reduces response latency for a chat application?

- A. Disabling streaming
- B. Using a smaller model, shorter prompts, and limiting output length
- C. Always choosing the largest model
- D. Adding thousands of tokens of unnecessary context

**Answer:** B

**Explanation:** Fewer input and output tokens and a lighter model speed up generation.

### D3-085
*Multiple Choice | Medium*

**Question:** A multilingual customer base needs support in many languages. What should the team check when selecting a model?

- A. The number of IAM roles
- B. Only the Region's name
- C. Which languages the model supports well and evaluation results in those languages
- D. Only the model's logo

**Answer:** C

**Explanation:** Language coverage and quality vary by model. Evaluate in the target languages before choosing.

### D3-086
*Multiple Choice | Medium*

**Question:** A document is longer than a model's context window. Which strategy helps?

- A. Ignore the limit
- B. Lower the top-p
- C. Raise the temperature
- D. Choose a model with a larger context window or split the document and use chunking, summarization, or retrieval

**Answer:** D

**Explanation:** Context limits are hard constraints. Use long-context models or map-reduce style summarization or RAG to handle long inputs.

### D3-087
*Multiple Choice | Medium*

**Question:** When creating a vector index for a knowledge base, which setting must align with the embeddings model?

- A. The IAM user name
- B. The bucket name
- C. The vector dimension size
- D. The VPC CIDR

**Answer:** C

**Explanation:** The index's vector dimensions must match the output dimension of the embedding model used for ingestion and queries.

### D3-088
*Multiple Choice | Medium*

**Question:** Why should the same embedding model be used for indexing documents and embedding user queries?

- A. Vectors from different models are not comparable, so similarity search would be unreliable
- B. It lowers storage cost
- C. It improves audio quality
- D. It removes the need for chunking

**Answer:** A

**Explanation:** Each model defines its own vector space. Mixing models breaks meaningful distance comparisons.

### D3-089
*Multiple Choice | Medium*

**Question:** In a retrieval step, what does the "number of retrieved results" (top-k) setting control?

- A. The model's temperature
- B. The number of users
- C. The number of epochs
- D. How many of the most similar chunks are fetched and added to the prompt

**Answer:** D

**Explanation:** Retrieving too few chunks may miss relevant context, and too many increases cost and noise.

### D3-090
*Multiple Choice | Medium*

**Question:** Why is it valuable for a RAG application to display source citations?

- A. It changes model weights
- B. It lets users verify answers and increases trust and transparency
- C. It speeds up embeddings
- D. It prevents all errors

**Answer:** B

**Explanation:** Citations point to the supporting documents, which helps users validate responses and supports auditing.

### D3-091
*Multiple Choice | Medium*

**Question:** Which Amazon Titan model type enables searching images with text queries and vice versa?

- A. Titan Text Lite
- B. Titan Multimodal Embeddings
- C. Titan Speech
- D. Amazon Polly

**Answer:** B

**Explanation:** Multimodal embeddings map text and images into a shared vector space so cross-modal similarity search is possible.

### D3-092
*True/False | Easy*

**Question:** Few-shot prompting places a few examples of the desired input and output in the prompt to guide the model's response.

- A. True
- B. False

**Answer:** True

**Explanation:** The examples show the model the task pattern, format, and tone, so it can imitate them without any weight updates.

### D3-093
*Multiple Choice | Hard*

**Question:** A RAG chatbot retrieves the correct passages, but its answers sometimes contradict them. Which control is most directly aimed at catching this problem?

- A. Using a contextual grounding check in Amazon Bedrock Guardrails
- B. Increasing top-k retrieval to the maximum
- C. Shortening the chunk size to one word
- D. Raising the temperature

**Answer:** A

**Explanation:** Contextual grounding checks compare the response with the supplied source content and flag claims that are unsupported or contradictory. Higher temperature would make contradictions more likely.

### D3-094
*Multiple Choice | Hard*

**Question:** A team has only about 50 labeled examples and wants to improve output quality for a new task. What is the most sensible first step?

- A. Pretrain a new foundation model
- B. Buy Provisioned Throughput first
- C. Try prompt engineering with those examples as few-shot demonstrations before considering fine-tuning
- D. Fine-tune immediately for 100 epochs

**Answer:** C

**Explanation:** With very little data, few-shot prompting is the cheapest, fastest approach and avoids overfitting risks. Fine-tuning generally benefits from larger curated datasets.

### D3-095
*True/False | Medium*

**Question:** Using larger and larger chunk sizes always improves retrieval quality in a RAG system.

- A. True
- B. False

**Answer:** False

**Explanation:** Very large chunks mix unrelated topics and dilute relevance, and they consume more of the context window. Chunk size should be tuned and evaluated.

### D3-096
*True/False | Medium*

**Question:** Prompt injection can originate from retrieved documents or web content, not only from the user's direct input.

- A. True
- B. False

**Answer:** True

**Explanation:** This is known as indirect prompt injection. Malicious instructions hidden in retrieved content can manipulate the model, so retrieved text must be treated as untrusted.

---

## Domain 4: Guidelines for Responsible AI

### D4-001
*Multiple Choice | Medium*

**Question:** Which list contains core dimensions of responsible AI as described by AWS?

- A. Speed, color, size, shape
- B. Encryption, backups, caching, routing
- C. Fairness, explainability, privacy and security, safety, controllability, veracity and robustness, governance, and transparency
- D. Latency, throughput, availability, durability

**Answer:** C

**Explanation:** AWS frames responsible AI around these dimensions. Each addresses a different class of risk, from biased outcomes to opaque decisions and unsafe behavior.

### D4-002
*Multiple Choice | Easy*

**Question:** What does the fairness dimension of responsible AI aim for?

- A. Lower cost
- B. Impartial outcomes that do not unjustly favor or disadvantage individuals or groups
- C. Larger datasets
- D. Faster inference

**Answer:** B

**Explanation:** Fairness considers the impact of AI on different stakeholder groups and works to prevent discriminatory outcomes.

### D4-003
*Multiple Choice | Medium*

**Question:** What does the privacy and security dimension emphasize?

- A. Maximizing data collection
- B. Removing authentication
- C. Publishing all training data
- D. Appropriately obtaining, using, and protecting data and models and preventing unauthorized access or misuse

**Answer:** D

**Explanation:** It covers consent, data protection, and securing models and pipelines from theft and attacks.

### D4-004
*Multiple Choice | Medium*

**Question:** What does the safety dimension of responsible AI address?

- A. Preventing harmful system output and misuse and reducing risk of harm to people and society
- B. Choosing colors
- C. Increasing output length
- D. Reducing GPU usage

**Answer:** A

**Explanation:** Safety focuses on avoiding harmful behaviors such as dangerous advice, toxic content, or unsafe actions.

### D4-005
*Multiple Choice | Medium*

**Question:** What does controllability refer to in responsible AI?

- A. Version control
- B. Control of hardware only
- C. Having mechanisms to monitor and steer the behavior of AI systems, including human oversight and the ability to intervene
- D. Price control

**Answer:** C

**Explanation:** Controllability ensures humans can align, correct, or stop systems when outputs or behaviors go wrong.

### D4-006
*Multiple Choice | Medium*

**Question:** What do veracity and robustness mean in responsible AI?

- A. Cost and availability
- B. Style and tone
- C. Speed and scale
- D. Producing accurate, reliable outputs and performing correctly even with unexpected or adversarial inputs

**Answer:** D

**Explanation:** Veracity concerns truthfulness and correctness. Robustness means stable behavior despite noise, edge cases, or attacks.

### D4-007
*Multiple Choice | Medium*

**Question:** What does the governance dimension cover?

- A. Only billing
- B. Only network design
- C. Processes, policies, roles, and accountability for managing AI risks and ensuring compliance across the lifecycle
- D. Only encryption keys

**Answer:** C

**Explanation:** Governance defines who is responsible, how risks are assessed, what standards apply, and how decisions are audited.

### D4-008
*Multiple Choice | Medium*

**Question:** What does transparency mean for responsible AI?

- A. Hiding model details
- B. Publishing source code only
- C. Making the UI transparent
- D. Openly communicating information about a system's capabilities, limitations, data, and decision-making so stakeholders can make informed choices

**Answer:** D

**Explanation:** Transparency allows users and regulators to understand what an AI system does and what its limitations are, for example through documentation such as model cards.

### D4-009
*Multiple Choice | Easy*

**Question:** In machine learning, what is bias?

- A. A hyperparameter
- B. The y-intercept only
- C. Faster training
- D. Systematic errors that lead to unfair or skewed outcomes for certain groups or situations

**Answer:** D

**Explanation:** Bias in data, models, or processes can produce discriminatory or inaccurate results for some groups.

### D4-010
*Multiple Choice | Medium*

**Question:** A training set for a voice assistant contains mostly recordings from one accent. This is an example of which kind of bias?

- A. Feature scaling bias
- B. Measurement bias
- C. Sampling (representation) bias
- D. Reward bias

**Answer:** C

**Explanation:** If the training sample does not represent the population the system will serve, performance will be poorer for underrepresented groups.

### D4-011
*Multiple Choice | Medium*

**Question:** A sensor consistently records values that are slightly inaccurate for one group of devices, skewing model inputs. Which type of bias is this?

- A. Confirmation bias
- B. Sampling bias
- C. Algorithmic bias
- D. Measurement bias

**Answer:** D

**Explanation:** Measurement bias arises when the data collection method or instrument systematically distorts values.

### D4-012
*Multiple Choice | Medium*

**Question:** A hiring model trained on past decisions reproduces a historical preference for certain candidates. Which bias is most evident?

- A. Selection bias
- B. Quantization bias
- C. Latency bias
- D. Historical (societal) bias

**Answer:** D

**Explanation:** Data that reflects past prejudices teaches models to replicate them, even when the data is accurate.

### D4-013
*Multiple Choice | Medium*

**Question:** What is confirmation bias in the context of building AI?

- A. Favoring data or interpretations that support pre-existing beliefs or hypotheses
- B. Confirming a model deployment
- C. Verifying hardware
- D. Confirming encryption

**Answer:** A

**Explanation:** Teams may unconsciously select or interpret data to confirm expectations, which skews models and evaluation.

### D4-014
*Multiple Choice | Medium*

**Question:** What is algorithmic bias?

- A. Higher temperature
- B. Unfair outcomes that arise from the design or optimization of the algorithm itself, such as proxies or objective choices
- C. A storage error
- D. A bug in network code

**Answer:** B

**Explanation:** Even with balanced data, choices such as the loss function, features, or thresholds can systematically disadvantage groups.

### D4-015
*Multiple Choice | Medium*

**Question:** What is selection bias?

- A. Selecting the best Region
- B. Selecting the cheapest instance
- C. Selecting hyperparameters
- D. A sample that is chosen non-randomly, so the training data does not reflect the true population

**Answer:** D

**Explanation:** Non-random selection, such as only surveying volunteers, makes the data unrepresentative.

### D4-016
*Multiple Choice | Medium*

**Question:** Which dataset characteristics help promote fairness and reduce bias?

- A. Small size, single source, and no documentation
- B. Only data from one region
- C. Only the most recent records
- D. Diversity, inclusivity, balanced representation, and curated data sources

**Answer:** D

**Explanation:** Datasets should represent the populations affected, be carefully sourced and documented, and be audited for imbalance.

### D4-017
*Multiple Choice | Medium*

**Question:** What can result from biased AI outputs?

- A. Discrimination, loss of customer trust, legal and reputational risk, and harm to individuals
- B. Lower cloud cost
- C. Improved accuracy for everyone
- D. Guaranteed profit

**Answer:** A

**Explanation:** Biased systems can violate regulations, harm people, and damage brand trust.

### D4-018
*Multiple Choice | Medium*

**Question:** Which SageMaker feature can detect bias in datasets before training?

- A. SageMaker Debugger
- B. SageMaker Neo
- C. SageMaker Clarify
- D. SageMaker Canvas only

**Answer:** C

**Explanation:** Clarify computes pre-training bias metrics, such as class imbalance, across facets (sensitive attributes) in the data.

### D4-019
*Multiple Choice | Medium*

**Question:** Which are examples of bias metrics that SageMaker Clarify can report?

- A. Disk IOPS and throughput
- B. Bucket size
- C. Class imbalance and difference in proportions of labels
- D. Number of epochs

**Answer:** C

**Explanation:** Clarify provides pre- and post-training bias metrics that quantify differences in outcomes or representation across groups.

### D4-020
*Multiple Choice | Medium*

**Question:** Which approach does SageMaker Clarify use to explain individual predictions?

- A. Feature attributions such as SHAP values
- B. Network packet capture
- C. Random sampling only
- D. Manual labeling

**Answer:** A

**Explanation:** SHAP-based attributions estimate how much each feature contributed to a prediction, which supports transparency and debugging.

### D4-021
*Multiple Choice | Medium*

**Question:** What do partial dependence plots (PDPs) show?

- A. The marginal effect of one or two features on the predicted outcome
- B. Training time
- C. Label counts
- D. Network traffic

**Answer:** A

**Explanation:** PDPs help interpret how a feature influences predictions on average, which supports explainability.

### D4-022
*Multiple Choice | Medium*

**Question:** Which service can monitor deployed models for bias drift and feature attribution drift over time?

- A. AWS Shield
- B. AWS Artifact
- C. Amazon Route 53
- D. SageMaker Model Monitor (with Clarify)

**Answer:** D

**Explanation:** Model Monitor integrates with Clarify to detect changes in bias metrics and feature importance after deployment.

### D4-023
*Multiple Choice | Medium*

**Question:** What does Amazon Augmented AI (A2I) provide for responsible AI?

- A. Data labeling only
- B. Faster GPUs
- C. Automated encryption
- D. Human-in-the-loop review of ML predictions to improve accuracy and provide oversight for sensitive decisions

**Answer:** D

**Explanation:** A2I routes low-confidence or sampled predictions to human reviewers, which supports controllability and safety.

### D4-024
*Multiple Choice | Medium*

**Question:** What is the purpose of SageMaker Model Cards?

- A. Model compression
- B. Credit card processing
- C. Increasing throughput
- D. Documenting a model's purpose, data, evaluation, limitations, and risk ratings to support transparency and governance

**Answer:** D

**Explanation:** Model Cards centralize key model information for stakeholders and audits.

### D4-025
*Multiple Choice | Medium*

**Question:** Which Bedrock capability helps prevent toxic or harmful content in model inputs and outputs?

- A. Amazon Macie
- B. AWS CloudFormation
- C. Amazon SQS
- D. Amazon Bedrock Guardrails

**Answer:** D

**Explanation:** Guardrails provide configurable filters for categories such as hate, insults, sexual content, violence, misconduct, and prompt attacks, plus denied topics and PII filters.

### D4-026
*Multiple Choice | Medium*

**Question:** What can Amazon Bedrock Model Evaluation help assess for responsible AI?

- A. Qualities such as accuracy, robustness, and toxicity of model outputs
- B. Bucket permissions
- C. Disk speed
- D. VPC routing

**Answer:** A

**Explanation:** Evaluation jobs can run built-in datasets and human review to test for toxicity, stereotyping, and other responsible AI dimensions.

### D4-027
*Multiple Choice | Medium*

**Question:** What is the difference between an interpretable model and an explainable model?

- A. An interpretable model is inherently understandable by design, while explainability often involves post hoc techniques applied to complex models
- B. They are identical
- C. Explainable models can never be accurate
- D. Interpretable models are always larger

**Answer:** A

**Explanation:** Linear models and small trees are interpretable by construction. For deep models, tools such as SHAP provide approximate explanations.

### D4-028
*Multiple Choice | Medium*

**Question:** Which describes a trade-off in responsible AI design?

- A. Safety always lowers cost
- B. Higher accuracy may reduce interpretability, and stricter safety filters may limit helpfulness
- C. Interpretability always increases accuracy
- D. There are no trade-offs

**Answer:** B

**Explanation:** Teams must balance competing goals such as performance versus explainability, and safety versus utility, based on risk and context.

### D4-029
*Multiple Choice | Medium*

**Question:** Which is a legal or business risk of generative AI?

- A. Higher availability
- B. Intellectual property infringement and loss of customer trust from inaccurate or biased outputs
- C. Faster development
- D. Lower hosting costs

**Answer:** B

**Explanation:** Generative AI can reproduce protected content, give inaccurate information, or produce biased or harmful outputs, which creates legal and reputational exposure.

### D4-030
*Multiple Choice | Medium*

**Question:** What is toxicity in generative AI outputs?

- A. A billing anomaly
- B. A security vulnerability
- C. Offensive, hateful, harassing, or otherwise harmful content generated by a model
- D. High GPU temperature

**Answer:** C

**Explanation:** Toxicity can appear when models mimic harmful patterns in training data. It is mitigated with curation, alignment, guardrails, and monitoring.

### D4-031
*Multiple Choice | Medium*

**Question:** Which approach best mitigates hallucinations in a customer-facing generative AI app?

- A. Hide errors from users
- B. Ground responses with RAG, add contextual grounding checks, cite sources, and use human review where risk is high
- C. Increase temperature
- D. Remove all system instructions

**Answer:** B

**Explanation:** Multiple layers of mitigation reduce unsupported claims, since no single technique eliminates hallucinations.

### D4-032
*Multiple Choice | Medium*

**Question:** What is data poisoning?

- A. Maliciously manipulating training data to corrupt a model's behavior
- B. Encrypting a dataset
- C. Deleting a dataset
- D. Slow queries

**Answer:** A

**Explanation:** Poisoned data can insert backdoors or bias. Defenses include data provenance, validation, and access controls.

### D4-033
*Multiple Choice | Medium*

**Question:** Which consideration is important when using open-source foundation models?

- A. They are always free of bias
- B. They have no licenses
- C. Their licenses may impose usage restrictions and carry risks that must be reviewed, such as unknown training data
- D. They never need evaluation

**Answer:** C

**Explanation:** Open models come with specific license terms and varying transparency about data, so legal and responsible AI reviews are still necessary.

### D4-034
*Multiple Choice | Medium*

**Question:** Which is an environmental consideration in responsible AI?

- A. Using more GPUs always lowers impact
- B. Training large models consumes significant energy, so efficient models, hardware, and Regions can reduce impact
- C. Ignoring utilization
- D. Choosing the logo color

**Answer:** B

**Explanation:** Sustainability can be improved by right-sizing models, using efficient accelerators, and reusing pretrained models rather than training from scratch.

### D4-035
*Multiple Choice | Hard*

**Question:** A facial analysis model has much higher error rates for people with darker skin tones. What is the most likely root cause?

- A. Training data that underrepresents those groups
- B. Too much regularization
- C. Excessive logging
- D. Using too many GPUs

**Answer:** A

**Explanation:** Underrepresentation in training data is a common cause of uneven performance. Improving data diversity and evaluating by subgroup are key remedies.

### D4-036
*Multiple Choice | Hard*

**Question:** A resume-screening model trained on past hiring data penalizes candidates from certain groups. Which type of bias does this most likely reflect?

- A. Hyperparameter bias
- B. Historical bias in the training data
- C. Compression bias
- D. Latency bias

**Answer:** B

**Explanation:** Past decisions embed societal preferences, and the model learns to replicate them.

### D4-037
*Multiple Choice | Hard*

**Question:** A lender must tell applicants why their loan was denied. Which capability is most relevant?

- A. Model distillation
- B. Larger context window
- C. Faster inference
- D. Model explainability, such as feature attributions with SageMaker Clarify

**Answer:** D

**Explanation:** Explainability tools show which factors most influenced a decision, which supports transparency and regulatory requirements.

### D4-038
*Multiple Choice | Hard*

**Question:** A customer-support chatbot occasionally produces offensive replies. Which controls are most appropriate?

- A. Raise temperature
- B. Remove monitoring
- C. Increase max tokens
- D. Add Guardrails content filters and keep monitoring and human escalation in place

**Answer:** D

**Explanation:** Filters block harmful content, while monitoring and escalation address residual failures.

### D4-039
*Multiple Choice | Hard*

**Question:** A clinical decision-support model has low confidence on certain cases. Which approach best supports safety?

- A. Ignore low-confidence cases
- B. Disable logging
- C. Route low-confidence predictions to human reviewers with Amazon A2I
- D. Always auto-approve

**Answer:** C

**Explanation:** Human review for uncertain, high-stakes cases provides oversight and reduces the risk of harm.

### D4-040
*Multiple Choice | Hard*

**Question:** A chatbot confidently tells customers about a refund policy that does not exist. Which issue is this, and what is a primary mitigation?

- A. Data drift; reduce epochs
- B. Underfitting; add layers
- C. Latency; add GPUs
- D. Hallucination; ground answers in authoritative policy documents with RAG and verify with guardrails

**Answer:** D

**Explanation:** The model fabricated plausible but false content. Grounding in trusted sources and checks reduces such errors.

### D4-041
*Multiple Choice | Hard*

**Question:** An image-generation feature produces output that closely imitates a living artist's protected work. Which risk is most directly raised?

- A. Network congestion
- B. Intellectual property infringement
- C. Hardware failure
- D. Storage cost

**Answer:** B

**Explanation:** Generative models may reproduce protected styles or content, which creates copyright risk and requires policy, filtering, and legal review.

### D4-042
*Multiple Choice | Medium*

**Question:** Which fairness metric compares the proportion of positive outcomes across groups?

- A. Demographic parity (difference in positive prediction rates)
- B. AUC only
- C. Mean squared error
- D. Perplexity

**Answer:** A

**Explanation:** Demographic parity checks whether groups receive positive outcomes at similar rates. Clarify reports related metrics such as difference in proportions of labels.

### D4-043
*Multiple Choice | Medium*

**Question:** Which technique can help reduce bias in a training dataset?

- A. Skipping data review
- B. Deleting all minority examples
- C. Using only one data source
- D. Resampling or reweighting underrepresented groups and collecting more representative data

**Answer:** D

**Explanation:** Balancing representation and improving data coverage mitigate skewed learning.

### D4-044
*Multiple Choice | Medium*

**Question:** Why is a diverse team valuable in AI development?

- A. Diverse perspectives help identify blind spots, biased assumptions, and harms that a homogeneous team might miss
- B. It speeds up GPUs
- C. It reduces cloud cost
- D. It removes the need for testing

**Answer:** A

**Explanation:** Inclusive teams improve problem framing, data review, and risk identification.

### D4-045
*Multiple Choice | Medium*

**Question:** What should transparency documentation for an AI system typically include?

- A. Passwords
- B. Intended use, training data sources, performance, known limitations, and risks
- C. Only the logo
- D. Source code only

**Answer:** B

**Explanation:** Documentation allows stakeholders to judge whether a system is appropriate for a given use and to understand its limits.

### D4-046
*Multiple Choice | Medium*

**Question:** Why should users be informed when they interact with an AI system or AI-generated content?

- A. It supports transparency, informed consent, and trust
- B. To reduce latency
- C. To lower costs
- D. To increase token usage

**Answer:** A

**Explanation:** Disclosure lets people calibrate their reliance on outputs and meets many regulatory expectations.

### D4-047
*Multiple Choice | Medium*

**Question:** What is automation bias (overreliance)?

- A. Bias from automation scripts
- B. A faster pipeline
- C. A storage setting
- D. The tendency to trust automated outputs too much, even when they are wrong

**Answer:** D

**Explanation:** Overreliance can lead to uncritical acceptance of model outputs, which is why human oversight and uncertainty communication matter.

### D4-048
*Multiple Choice | Medium*

**Question:** What is red teaming in the context of AI?

- A. Deploying to production quickly
- B. Deliberately probing a system with adversarial or harmful inputs to discover vulnerabilities and unsafe behaviors
- C. Painting servers red
- D. Auditing invoices

**Answer:** B

**Explanation:** Red teams simulate attackers and misuse, such as jailbreaks, to find weaknesses before real users do.

### D4-049
*Multiple Choice | Medium*

**Question:** What is an adversarial example?

- A. A well-labeled sample
- B. A duplicate record
- C. An input deliberately crafted, often with subtle changes, to cause a model to make mistakes
- D. A sample from the test set

**Answer:** C

**Explanation:** Small perturbations can mislead models. Robustness testing and adversarial training improve resilience.

### D4-050
*Multiple Choice | Medium*

**Question:** What does robustness mean for an AI model?

- A. It trains slowly
- B. It uses more memory
- C. It maintains reliable performance when faced with noisy, unexpected, or adversarial inputs
- D. It is expensive

**Answer:** C

**Explanation:** A robust system degrades gracefully and resists manipulation.

### D4-051
*Multiple Choice | Medium*

**Question:** Why is continuous monitoring part of responsible AI?

- A. Monitoring is only for cost
- B. Behavior and data can drift after deployment, so ongoing checks are needed for accuracy, fairness, and safety
- C. Regulators ban monitoring
- D. Models never change

**Answer:** B

**Explanation:** Real-world conditions change. Monitoring detects drift, bias drift, and emerging harms so teams can respond.

### D4-052
*Multiple Choice | Medium*

**Question:** What is a feedback loop that can amplify bias?

- A. Model outputs influence future training data in a way that reinforces existing patterns, such as predictive policing sending more patrols to already flagged areas
- B. A cache
- C. A CI pipeline
- D. A DNS record

**Answer:** A

**Explanation:** When predictions shape the data collected next, small biases can compound over time.

### D4-053
*Multiple Choice | Medium*

**Question:** Why is explainability particularly challenging for large language models?

- A. They have too few parameters
- B. They are too small
- C. They have billions of parameters and complex learned representations that make individual outputs hard to trace
- D. They only use rules

**Answer:** C

**Explanation:** The scale and opacity of LLMs make attribution difficult. Techniques such as citations, grounding, and reasoning traces provide partial transparency.

### D4-054
*True/False | Medium*

**Question:** A model can have high overall accuracy yet perform poorly for a specific subgroup.

- A. True
- B. False

**Answer:** True

**Explanation:** Aggregate metrics can hide subgroup disparities, so evaluation should be disaggregated across relevant groups.

### D4-055
*True/False | Medium*

**Question:** If a model is explainable, governance processes are no longer necessary.

- A. True
- B. False

**Answer:** False

**Explanation:** Explainability is one tool among many. Governance covers policies, accountability, risk assessment, and compliance across the lifecycle.

### D4-056
*True/False | Medium*

**Question:** Human oversight is a component of many responsible AI practices, especially for high-risk decisions.

- A. True
- B. False

**Answer:** True

**Explanation:** Human-in-the-loop review and the ability to override or stop systems support safety and accountability.

### D4-057
*True/False | Medium*

**Question:** Responsible AI practices only need to be applied right before deployment.

- A. True
- B. False

**Answer:** False

**Explanation:** They should be integrated throughout the lifecycle: design, data collection, training, evaluation, deployment, and monitoring.

### D4-058
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO actions help mitigate dataset bias? (Select TWO.)

- A. Use resampling or reweighting for underrepresented groups
- B. Remove documentation about data sources
- C. Train only on data from the largest group
- D. Collect more diverse and representative data
- E. Skip subgroup evaluation

**Answer:** A, D

**Explanation:** Improving representation and balancing the data reduce skew. Ignoring subgroups or documentation worsens the risk.

### D4-059
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO capabilities does SageMaker Clarify provide? (Select TWO.)

- A. Explaining model predictions with feature attributions
- B. Detecting bias in data and models
- C. Compiling models for edge devices
- D. Labeling images with human workforces
- E. Hosting vector databases

**Answer:** A, B

**Explanation:** Clarify supports bias detection and explainability. Labeling is Ground Truth, and edge compilation is Neo.

### D4-060
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO are risks commonly associated with generative AI outputs? (Select TWO.)

- A. Zero latency
- B. Toxic or biased content
- C. Guaranteed accuracy
- D. Perfect determinism
- E. Hallucinations

**Answer:** B, E

**Explanation:** Generative models can fabricate facts and produce harmful or biased content, which makes mitigation and monitoring essential.

### D4-061
*Multiple Choice | Medium*

**Question:** Which Guardrails content filter categories are available for harmful content?

- A. Compression and caching
- B. CPU and memory
- C. Hate, insults, sexual, violence, misconduct, and prompt attacks
- D. Latency and throughput

**Answer:** C

**Explanation:** Guardrails offers configurable strengths for these categories on both inputs and outputs.

### D4-062
*Multiple Choice | Medium*

**Question:** What does adjusting the strength of a Guardrails content filter do?

- A. Changes how aggressively content in that category is blocked, trading off safety and permissiveness
- B. Changes the Region
- C. Changes the model's size
- D. Changes the token price

**Answer:** A

**Explanation:** Higher strength blocks more borderline content. The right level depends on the application's audience and risk.

### D4-063
*Multiple Choice | Medium*

**Question:** Which Guardrails feature can block specific profanity or custom phrases?

- A. Contextual grounding
- B. Provisioned Throughput
- C. Embeddings
- D. Word filters

**Answer:** D

**Explanation:** Word filters let you define words or phrases to block, such as profanity or competitor names.

### D4-064
*Multiple Choice | Medium*

**Question:** Which capability supports privacy by detecting and masking personal information in prompts and responses?

- A. Temperature tuning
- B. Model distillation
- C. Guardrails sensitive information filters
- D. Chunking

**Answer:** C

**Explanation:** PII filters can detect entities such as names, emails, and account numbers and either block or mask them.

### D4-065
*Multiple Choice | Medium*

**Question:** Which principle supports privacy by limiting what is collected and retained?

- A. Data minimization
- B. Share broadly
- C. Retain forever
- D. Collect as much as possible

**Answer:** A

**Explanation:** Collect and keep only what is needed for the purpose, which reduces exposure if data is compromised.

### D4-066
*Multiple Choice | Medium*

**Question:** Why is obtaining proper consent and ensuring ethical sourcing of training data important?

- A. It increases epochs
- B. It lowers GPU cost
- C. It respects individuals' rights and reduces legal and reputational risk
- D. It speeds up inference

**Answer:** C

**Explanation:** Data should be collected lawfully and ethically, with attention to rights, licensing, and privacy.

### D4-067
*Multiple Choice | Medium*

**Question:** What is the purpose of an AI impact assessment before deployment?

- A. To choose hardware
- B. To set prices
- C. To reduce training time
- D. To evaluate potential benefits, harms, affected stakeholders, and risks, and to define mitigations

**Answer:** D

**Explanation:** Impact assessments identify risks early, which informs design choices, controls, and go/no-go decisions.

### D4-068
*Multiple Choice | Medium*

**Question:** Why should stakeholders, including affected users, be engaged during AI design?

- A. To surface needs, concerns, and potential harms early and build systems that serve those affected
- B. To raise costs
- C. To hide risks
- D. To avoid testing

**Answer:** A

**Explanation:** Participatory design improves relevance and reduces unforeseen harm.

### D4-069
*Multiple Choice | Medium*

**Question:** What should be evaluated when selecting a model from a responsible AI perspective?

- A. Only the number of parameters
- B. Safety evaluations, bias and toxicity results, transparency about training data, license terms, and fit for the intended use
- C. Only the brand
- D. Only the price

**Answer:** B

**Explanation:** Responsible selection looks beyond raw capability to risk, documentation, and legal terms.

### D4-070
*Multiple Choice | Medium*

**Question:** What is a typical trade-off between open-source and proprietary models related to transparency?

- A. Proprietary models are always more transparent
- B. Open models are always safer
- C. There is no difference
- D. Open models can offer more visibility into architecture or weights, while proprietary models may provide limited detail but come with vendor safeguards and support

**Answer:** D

**Explanation:** The right choice depends on the need for inspection and customization versus managed safety features and support.

### D4-071
*Multiple Choice | Medium*

**Question:** What does accountability mean in AI governance?

- A. Allowing anonymous changes
- B. Clearly assigning ownership and responsibility for AI system outcomes and decisions
- C. Automating all approvals
- D. Billing for usage

**Answer:** B

**Explanation:** Defined roles and audit trails make it possible to answer for the system's behavior and to correct issues.

### D4-072
*Multiple Choice | Medium*

**Question:** What can SageMaker Model Monitor detect in production that is relevant to responsible AI?

- A. Only DNS errors
- B. Only storage cost
- C. Only IAM changes
- D. Changes in data quality, model quality, and bias or feature attribution drift

**Answer:** D

**Explanation:** Ongoing checks identify when a model's behavior or fairness characteristics deviate from baselines.

### D4-073
*Multiple Choice | Medium*

**Question:** What is model alignment?

- A. Ensuring a model's behavior matches human intentions and values, often through techniques such as RLHF and safety tuning
- B. Aligning text on a page
- C. Aligning data columns
- D. Aligning servers in a rack

**Answer:** A

**Explanation:** Alignment techniques steer models toward helpful, honest, and harmless behavior.

### D4-074
*Multiple Choice | Medium*

**Question:** Why should evaluation datasets be inclusive and representative?

- A. To speed up training
- B. To reduce data size
- C. To avoid documentation
- D. To measure fairness and performance across all groups the system will serve

**Answer:** D

**Explanation:** Evaluating only on a narrow population can hide failures that affect underrepresented users.

### D4-075
*Multiple Choice | Medium*

**Question:** How can annotator bias be reduced when labeling data?

- A. Skip quality checks
- B. Use a single annotator
- C. Automate without review
- D. Provide clear guidelines, use diverse annotators, and apply consensus and quality review

**Answer:** D

**Explanation:** Diverse workforces and multi-annotator consensus reduce idiosyncratic judgments. Ground Truth supports these workflows.

### D4-076
*Multiple Choice | Medium*

**Question:** What is differential privacy?

- A. A pricing tier
- B. A way to compress data
- C. A technique that adds calibrated noise so individual records cannot be identified from outputs or aggregates
- D. A way to increase accuracy

**Answer:** C

**Explanation:** Differential privacy offers mathematical guarantees that the presence or absence of one person's data has limited influence on results.

### D4-077
*Multiple Choice | Medium*

**Question:** How can synthetic data help with responsible AI?

- A. It removes the need for testing
- B. It can augment underrepresented groups or reduce the use of sensitive real data, though it must be validated to avoid introducing new bias
- C. It is always identical to real data
- D. It guarantees fairness

**Answer:** B

**Explanation:** Synthetic data is a useful tool but needs quality and bias checks.

### D4-078
*Multiple Choice | Medium*

**Question:** Which technique can estimate local explanations of individual model predictions by approximating the model near a data point?

- A. Dropout
- B. One-hot encoding
- C. LIME (Local Interpretable Model-agnostic Explanations)
- D. Backpropagation

**Answer:** C

**Explanation:** LIME fits a simple interpretable model around a prediction to explain it, and it is model-agnostic.

### D4-079
*Multiple Choice | Medium*

**Question:** Which of the following is an inherently interpretable model type?

- A. Decision tree or linear regression
- B. Billion-parameter transformer
- C. Large deep neural network
- D. Ensemble of thousands of deep nets

**Answer:** A

**Explanation:** The structure of trees and linear models can be inspected directly to understand how predictions are made.

### D4-080
*Multiple Choice | Medium*

**Question:** What does feature importance help explain?

- A. The number of users
- B. The hardware used
- C. The Region
- D. Which input features contribute most to a model's predictions

**Answer:** D

**Explanation:** It supports transparency and debugging by highlighting influential variables, which can also reveal proxies for sensitive attributes.

### D4-081
*Multiple Choice | Medium*

**Question:** How does the Amazon Titan Image Generator support transparency regarding AI-generated images?

- A. It deletes the images
- B. It prevents all image generation
- C. It blocks downloads
- D. It embeds an invisible watermark in generated images by default to help identify them as AI-generated

**Answer:** D

**Explanation:** Watermarking helps trace the origin of content and reduces misinformation risk.

### D4-082
*Multiple Choice | Medium*

**Question:** Which risk is associated with deepfakes and synthetic media?

- A. Faster networks
- B. Better compression
- C. Smaller file sizes
- D. Misinformation, impersonation, and erosion of trust

**Answer:** D

**Explanation:** Realistic synthetic media can mislead or defraud, so provenance and watermarking, and detection and policy controls, are important.

### D4-083
*Multiple Choice | Medium*

**Question:** For a customer-facing chatbot handling sensitive issues, which design supports controllability and safety?

- A. Remove all filters
- B. Hide that it is AI
- C. Never allow handoff
- D. Provide an escalation path to a human agent for sensitive or low-confidence situations

**Answer:** D

**Explanation:** Human handoff ensures that complex or high-risk cases get appropriate care.

### D4-084
*Multiple Choice | Medium*

**Question:** What does the safety dimension aim to prevent?

- A. Fast responses
- B. High availability
- C. Harmful outputs and misuse
- D. Low costs

**Answer:** C

**Explanation:** Safety work reduces the chance that systems cause physical, psychological, or societal harm.

### D4-085
*Multiple Choice | Medium*

**Question:** Which of the following is NOT a bias mitigation technique?

- A. Training only on the majority group and ignoring subgroup performance
- B. Evaluating metrics across demographic groups
- C. Rebalancing the dataset
- D. Auditing data sources

**Answer:** A

**Explanation:** Ignoring subgroups exacerbates bias. The other options are accepted mitigation or detection practices.

### D4-086
*Multiple Choice | Medium*

**Question:** What does the veracity dimension emphasize?

- A. Network
- B. Truthfulness and factual correctness of system outputs
- C. Storage
- D. Speed

**Answer:** B

**Explanation:** Veracity concerns that outputs are accurate and reliable, which is why grounding, evaluation, and verification matter.

### D4-087
*Multiple Choice | Medium*

**Question:** Why should high-stakes decisions, such as loan denials or medical triage, include human review?

- A. To catch model errors and bias, provide accountability, and handle edge cases
- B. It lowers cost
- C. Humans are faster
- D. It reduces storage

**Answer:** A

**Explanation:** Humans provide judgment, context, and recourse, and they are essential where errors cause significant harm.

### D4-088
*Multiple Choice | Medium*

**Question:** What problem can arise when a classification dataset has heavily imbalanced classes?

- A. Lower energy use
- B. Faster training only
- C. Perfect accuracy for all classes
- D. The model may perform well on the majority class but poorly on the minority class, which causes unfair or unsafe outcomes

**Answer:** D

**Explanation:** Without mitigation, the model can learn to favor the majority class, which hurts minority groups or rare events.

### D4-089
*Multiple Choice | Medium*

**Question:** How do AWS AI Service Cards differ from SageMaker Model Cards?

- A. They are the same
- B. Service Cards are published by AWS for its managed AI services, while Model Cards are created by customers to document their own models
- C. Model Cards are published by AWS only
- D. Service Cards document customer models

**Answer:** B

**Explanation:** Service Cards describe AWS-provided services, while Model Cards let customers record details for models they build or fine-tune.

### D4-090
*Multiple Choice | Medium*

**Question:** At which stages of the AI lifecycle should responsible AI be considered?

- A. Only after incidents
- B. Only at deployment
- C. Only during training
- D. Throughout design, data collection, development, evaluation, deployment, and monitoring

**Answer:** D

**Explanation:** Responsible AI is a continuous practice integrated at every stage, not a one-time review.

### D4-091
*Multiple Choice | Medium*

**Question:** What can Amazon Bedrock human evaluation workflows use?

- A. Only automated metrics
- B. Only AWS staff
- C. Your own workforce or an AWS-managed team to rate model responses on criteria such as helpfulness and style
- D. Only open-source tools

**Answer:** C

**Explanation:** Human evaluation jobs collect ratings from reviewers to complement automatic metrics.

### D4-092
*Multiple Choice | Medium*

**Question:** Which ethical consideration applies when using personal content to train or fine-tune models?

- A. Using the largest dataset regardless of source
- B. Publishing the data
- C. Respecting privacy, consent, and licensing for the data used
- D. Ignoring copyright

**Answer:** C

**Explanation:** Teams must ensure they have the right to use data and that it is handled lawfully and ethically.

### D4-093
*Multiple Choice | Hard*

**Question:** A hospital considers a highly accurate but opaque deep model versus a slightly less accurate, interpretable model for diagnosis support. Which factor should weigh most in the decision?

- A. Only the training speed
- B. The need for clinicians to understand and trust predictions, regulatory expectations, and the risk of error
- C. Only the model's file size
- D. Only the cloud Region

**Answer:** B

**Explanation:** In high-stakes domains, explainability and accountability may outweigh small accuracy gains. The trade-off should be decided based on risk.

### D4-094
*True/False | Easy*

**Question:** Biased training data can lead to unfair outcomes in a model's predictions.

- A. True
- B. False

**Answer:** True

**Explanation:** Models learn patterns from their data, including skewed representation or historical prejudice, and can reproduce or amplify those patterns in their outputs.

### D4-095
*True/False | Easy*

**Question:** Transparency in responsible AI includes openly communicating a system's capabilities, limitations, and intended use.

- A. True
- B. False

**Answer:** True

**Explanation:** Clear communication, such as through model cards and service cards, lets stakeholders judge whether a system is appropriate and trustworthy.

### D4-096
*Multiple Choice | Easy*

**Question:** Which responsible AI dimension focuses on being able to describe how a model arrived at its output?

- A. Explainability
- B. Durability
- C. Scalability
- D. Availability

**Answer:** A

**Explanation:** Explainability provides human-understandable reasons for predictions, which supports trust, debugging, and regulatory compliance.

### D4-097
*Multiple Choice | Hard*

**Question:** A loan model has similar overall accuracy for two demographic groups, yet it approves equally qualified applicants from one group at a much lower rate. Which concern does this best illustrate?

- A. Data drift only
- B. Hyperparameter tuning
- C. A fairness problem in the form of disparate outcomes between groups
- D. Underfitting

**Answer:** C

**Explanation:** Overall accuracy can hide unequal treatment. Group-level metrics, such as differences in approval rates, reveal fairness gaps that must be investigated and mitigated.

### D4-098
*True/False | Medium*

**Question:** Because a very large model is highly capable, its generative AI outputs can safely be used for high-stakes decisions without human review.

- A. True
- B. False

**Answer:** False

**Explanation:** Large models still hallucinate and can be biased. High-stakes uses call for human oversight, validation, and accountability.

---

## Domain 5: Security, Compliance, and Governance

### D5-001
*Multiple Choice | Medium*

**Question:** When using Amazon Bedrock, which of the following is the customer's responsibility under the shared responsibility model?

- A. Patching the underlying hypervisors
- B. Managing access permissions, protecting their data, and configuring guardrails and application security
- C. Operating the global network backbone
- D. Maintaining the physical data centers

**Answer:** B

**Explanation:** AWS manages the underlying service infrastructure, while customers control who can invoke models, how data is handled, and how applications are secured.

### D5-002
*Multiple Choice | Easy*

**Question:** What does the principle of least privilege mean?

- A. Sharing one account among all users
- B. Granting administrator access to everyone
- C. Granting only the minimum permissions required to perform a task
- D. Disabling all permissions

**Answer:** C

**Explanation:** Limiting permissions reduces the blast radius of mistakes or compromised credentials.

### D5-003
*Multiple Choice | Medium*

**Question:** Why are IAM roles generally preferred over long-term access keys for applications running on AWS?

- A. Roles remove all permissions
- B. Roles provide temporary credentials that are automatically rotated
- C. Roles disable logging
- D. Roles are free

**Answer:** B

**Explanation:** Temporary credentials reduce the risk of leaked, long-lived secrets.

### D5-004
*Multiple Choice | Medium*

**Question:** What additional protection does multi-factor authentication (MFA) provide?

- A. Faster API calls
- B. A second verification factor beyond a password, which reduces the risk of account takeover
- C. Cheaper storage
- D. Higher model accuracy

**Answer:** B

**Explanation:** MFA helps prevent unauthorized access even if a password is compromised.

### D5-005
*Multiple Choice | Medium*

**Question:** What are service control policies (SCPs) in AWS Organizations used for?

- A. Encrypting objects
- B. Setting maximum permission guardrails across accounts in an organization
- C. Labeling data
- D. Scanning for malware

**Answer:** B

**Explanation:** SCPs define the upper limit of what accounts can do, for example denying use of unapproved AI services or Regions, regardless of IAM policies.

### D5-006
*Multiple Choice | Medium*

**Question:** Which service is used to create and control encryption keys for encrypting data at rest across AWS services?

- A. AWS Key Management Service (AWS KMS)
- B. Amazon Lex
- C. Amazon Polly
- D. AWS Glue

**Answer:** A

**Explanation:** KMS manages cryptographic keys and integrates with S3, SageMaker, Bedrock, and many other services.

### D5-007
*Multiple Choice | Medium*

**Question:** Which mechanism protects data as it travels between a client and an AWS service endpoint?

- A. Tagging
- B. Encryption in transit using TLS
- C. Disk partitioning
- D. Data cataloging

**Answer:** B

**Explanation:** TLS encrypts traffic on the network so data cannot be read if intercepted.

### D5-008
*Multiple Choice | Medium*

**Question:** Why might a company choose customer managed KMS keys instead of AWS managed keys?

- A. They provide greater control over key policies, rotation, and the ability to audit and disable keys
- B. They make models faster
- C. They remove the need for IAM
- D. They are free

**Answer:** A

**Explanation:** Customer managed keys give explicit control and audit capability, which is often required for compliance.

### D5-009
*Multiple Choice | Medium*

**Question:** How can customers encrypt the artifacts of a custom model created in Amazon Bedrock?

- A. It is not possible
- B. By deleting the model
- C. By emailing keys
- D. By specifying a customer managed AWS KMS key for the customization job and resulting model

**Answer:** D

**Explanation:** Bedrock supports KMS encryption for customization jobs and custom model artifacts, as well as for stored data such as knowledge base content.

### D5-010
*Multiple Choice | Medium*

**Question:** What do AWS PrivateLink and VPC interface endpoints enable for Amazon Bedrock?

- A. Public internet exposure
- B. Free usage
- C. Faster training only
- D. Private connectivity from a VPC to Bedrock without traversing the public internet

**Answer:** D

**Explanation:** Interface endpoints keep traffic on the AWS network, which helps meet security and compliance requirements.

### D5-011
*Multiple Choice | Medium*

**Question:** Which AWS network controls restrict traffic to and from resources within a VPC?

- A. IAM users
- B. Security groups and network ACLs
- C. CloudFormation templates
- D. AWS Artifact

**Answer:** B

**Explanation:** Security groups are stateful instance-level firewalls, and network ACLs are stateless subnet-level controls.

### D5-012
*Multiple Choice | Medium*

**Question:** Which service records API calls and account activity for auditing and governance, including calls to Amazon Bedrock?

- A. AWS CloudTrail
- B. Amazon Kendra
- C. AWS Glue
- D. Amazon Polly

**Answer:** A

**Explanation:** CloudTrail logs who called which API, when, and from where, which supports audits and security investigations.

### D5-013
*Multiple Choice | Medium*

**Question:** Which service collects metrics and logs, and sets alarms, to monitor applications and models?

- A. AWS Shield
- B. Amazon CloudWatch
- C. AWS Audit Manager
- D. AWS Artifact

**Answer:** B

**Explanation:** CloudWatch provides observability for operational and security monitoring, including Bedrock and SageMaker metrics.

### D5-014
*Multiple Choice | Medium*

**Question:** What does Amazon Bedrock model invocation logging provide?

- A. Automatic fine-tuning
- B. Free tokens
- C. The ability to capture prompts, responses, and metadata in Amazon S3 or CloudWatch Logs for auditing and analysis
- D. Faster inference

**Answer:** C

**Explanation:** Invocation logging helps with auditing, troubleshooting, and compliance. Logs themselves must be protected because they can contain sensitive content.

### D5-015
*Multiple Choice | Medium*

**Question:** What does AWS Config do?

- A. Trains models
- B. Labels data
- C. Records resource configurations and evaluates them against rules for compliance and drift
- D. Translates text

**Answer:** C

**Explanation:** Config continuously assesses whether resources, such as S3 buckets or encryption settings, meet desired configurations.

### D5-016
*Multiple Choice | Medium*

**Question:** What does AWS Audit Manager help with?

- A. Continuously collecting evidence to help assess compliance with frameworks and regulations
- B. Image labeling
- C. Billing
- D. Model training

**Answer:** A

**Explanation:** Audit Manager automates evidence collection and maps it to controls, which simplifies audit preparation.

### D5-017
*Multiple Choice | Medium*

**Question:** What is AWS Artifact?

- A. A code compiler
- B. A vector database
- C. A model registry
- D. A portal for on-demand access to AWS compliance reports and agreements

**Answer:** D

**Explanation:** Artifact provides audit artifacts such as SOC and ISO reports and lets customers accept agreements such as business associate addendums.

### D5-018
*Multiple Choice | Medium*

**Question:** What does Amazon Inspector do?

- A. Automatically scans workloads such as EC2 instances, container images, and Lambda functions for software vulnerabilities and unintended exposure
- B. Translates content
- C. Labels images
- D. Hosts models

**Answer:** A

**Explanation:** Inspector provides continuous vulnerability management and helps secure the compute used for ML and generative AI applications.

### D5-019
*Multiple Choice | Medium*

**Question:** What does AWS Trusted Advisor provide?

- A. Checks and recommendations on cost, performance, security, fault tolerance, and service quotas
- B. Speech synthesis
- C. Image recognition
- D. Model training

**Answer:** A

**Explanation:** Trusted Advisor inspects the environment against best practices and flags issues such as open security groups.

### D5-020
*Multiple Choice | Medium*

**Question:** Which service helps store, rotate, and retrieve secrets such as API keys and database credentials?

- A. AWS Secrets Manager
- B. Amazon Translate
- C. Amazon Polly
- D. Amazon Lex

**Answer:** A

**Explanation:** Secrets Manager avoids hard-coding credentials and supports automatic rotation.

### D5-021
*Multiple Choice | Medium*

**Question:** Which service provides intelligent threat detection by analyzing logs and activity for malicious behavior?

- A. Amazon Personalize
- B. Amazon GuardDuty
- C. Amazon Polly
- D. AWS Glue

**Answer:** B

**Explanation:** GuardDuty monitors CloudTrail, VPC flow logs, and DNS logs to detect suspicious behavior such as unusual API calls.

### D5-022
*Multiple Choice | Medium*

**Question:** Which service aggregates and prioritizes security findings from multiple AWS services and partner tools?

- A. AWS Security Hub
- B. Amazon Polly
- C. Amazon Transcribe
- D. Amazon Lex

**Answer:** A

**Explanation:** Security Hub gives a centralized view of security posture and compliance checks across accounts.

### D5-023
*Multiple Choice | Medium*

**Question:** What is the purpose of a data catalog, such as the AWS Glue Data Catalog, in data governance?

- A. To translate text
- B. To compress files
- C. To provide a searchable inventory of datasets and metadata, which makes it easier to discover and govern data
- D. To store credentials

**Answer:** C

**Explanation:** Cataloging improves discoverability, ownership tracking, and policy application across data assets.

### D5-024
*Multiple Choice | Medium*

**Question:** What is data lineage?

- A. The speed of a network
- B. A record of where data came from and how it was transformed, which supports traceability and auditing
- C. The size of a dataset
- D. The color of a dashboard

**Answer:** B

**Explanation:** Lineage lets teams trace outputs back to sources, which helps with debugging, compliance, and trust.

### D5-025
*Multiple Choice | Medium*

**Question:** Why is documenting data provenance and source citations important for AI applications?

- A. It makes models larger
- B. It provides traceability to the origin of information, supporting accuracy, accountability, and compliance
- C. It disables logging
- D. It increases token usage

**Answer:** B

**Explanation:** Knowing where data and answers come from lets organizations verify, audit, and correct them.

### D5-026
*Multiple Choice | Medium*

**Question:** Which practices are part of secure data engineering for AI?

- A. Sharing credentials
- B. Disabling encryption
- C. Copying data to personal drives
- D. Assessing data quality, applying privacy-enhancing technologies, controlling access, and protecting data integrity

**Answer:** D

**Explanation:** These measures help ensure that training and retrieval data are accurate, protected, and used appropriately.

### D5-027
*Multiple Choice | Medium*

**Question:** What is the difference between data masking and tokenization?

- A. Tokenization compresses data
- B. Masking encrypts the disk
- C. They are identical
- D. Masking obscures data values, for example by replacing characters, while tokenization replaces data with non-sensitive tokens that can map back to the original in a secured vault

**Answer:** D

**Explanation:** Both reduce exposure of sensitive data. The choice depends on whether the original must be recoverable.

### D5-028
*Multiple Choice | Medium*

**Question:** What does data residency refer to?

- A. The speed of the network
- B. The cost of storage
- C. The color of the data
- D. The geographic location where data is stored and processed, which may be restricted by regulation

**Answer:** D

**Explanation:** Many regulations require data to remain in specific countries or Regions, so choosing AWS Regions, including for inference, matters.

### D5-029
*Multiple Choice | Medium*

**Question:** Which S3 feature helps prevent accidental public exposure of buckets containing training data?

- A. S3 Transfer Acceleration
- B. S3 Intelligent-Tiering
- C. S3 Select
- D. S3 Block Public Access

**Answer:** D

**Explanation:** Block Public Access overrides policies and ACLs that would otherwise make buckets or objects public.

### D5-030
*Multiple Choice | Medium*

**Question:** Which AWS service provides fine-grained access control, down to table, column, or row, for data lakes used in analytics and ML?

- A. AWS Shield
- B. Amazon Lex
- C. AWS Lake Formation
- D. Amazon Polly

**Answer:** C

**Explanation:** Lake Formation centralizes permissions on data lake resources so that users and services only see authorized data.

### D5-031
*Multiple Choice | Medium*

**Question:** Which of the following is on the OWASP Top 10 for LLM applications?

- A. Slow DNS
- B. Low CPU
- C. Prompt injection
- D. Large file size

**Answer:** C

**Explanation:** Prompt injection is a leading risk. Others include insecure output handling, training data poisoning, model denial of service, supply chain vulnerabilities, sensitive information disclosure, excessive agency, and model theft.

### D5-032
*Multiple Choice | Medium*

**Question:** What is insecure output handling in LLM applications?

- A. Compressed output
- B. Passing model output to downstream systems without validation, which can enable attacks such as injection or code execution
- C. Short output
- D. Fast output

**Answer:** B

**Explanation:** Treat model output as untrusted input. Validate and sanitize before using it in browsers, shells, databases, or APIs.

### D5-033
*Multiple Choice | Medium*

**Question:** What is model theft?

- A. Renaming a model
- B. Updating a model
- C. Deleting a model
- D. Unauthorized access to or extraction of proprietary model weights or behavior

**Answer:** D

**Explanation:** Protect model artifacts with access controls and encryption, and limit queries that could enable extraction.

### D5-034
*Multiple Choice | Medium*

**Question:** What does excessive agency mean for an LLM-based agent?

- A. The agent has no logging
- B. The agent runs too slowly
- C. The agent responds too briefly
- D. The agent has more permissions, functionality, or autonomy than needed, which increases harm if it is manipulated

**Answer:** D

**Explanation:** Limit tools and permissions to the minimum required and require human approval for high-impact actions.

### D5-035
*Multiple Choice | Medium*

**Question:** What is sensitive information disclosure in an LLM application?

- A. A billing alert
- B. A UI bug
- C. Faster generation
- D. The model revealing confidential data, such as PII or secrets, from training data, prompts, or retrieved context

**Answer:** D

**Explanation:** Mitigations include data minimization, filtering, access controls, and keeping secrets out of prompts.

### D5-036
*Multiple Choice | Medium*

**Question:** How can an application reduce the risk of denial-of-service or runaway costs from excessive LLM requests?

- A. Increase max tokens
- B. Disable all limits
- C. Implement rate limiting, quotas, input size limits, and monitoring
- D. Allow unlimited anonymous access

**Answer:** C

**Explanation:** Throttling and quotas protect availability and cost. AWS WAF and API Gateway usage plans can help.

### D5-037
*Multiple Choice | Medium*

**Question:** Which AWS service helps protect web applications and APIs that front generative AI features from common web exploits and bots?

- A. Amazon Lex
- B. AWS WAF
- C. Amazon Polly
- D. Amazon Transcribe

**Answer:** B

**Explanation:** AWS WAF filters malicious requests and supports rate-based rules before they reach the application.

### D5-038
*Multiple Choice | Medium*

**Question:** In the Generative AI Security Scoping Matrix, what best describes consuming a pretrained foundation model through an API, such as Amazon Bedrock, to build your own application?

- A. Using a third-party SaaS only
- B. Building an application on top of a pretrained model, where the customer focuses on securing the application, data, and access
- C. Training a model from scratch
- D. A consumer application with no customization

**Answer:** B

**Explanation:** When using pretrained models through managed APIs, the provider secures the model hosting, while the customer secures prompts, data, identity, and application logic.

### D5-039
*Multiple Choice | Medium*

**Question:** Which are examples of compliance standards or regulations relevant to AI workloads?

- A. TCP/IP
- B. JPEG
- C. ISO 27001, SOC 2, GDPR, and HIPAA
- D. HTML5

**Answer:** C

**Explanation:** Organizations must map AI workloads to standards such as ISO, SOC, GDPR, and HIPAA, depending on industry and geography.

### D5-040
*Multiple Choice | Medium*

**Question:** What is ISO/IEC 42001?

- A. A programming language
- B. A network protocol
- C. A compression standard
- D. An international standard for AI management systems that helps organizations govern AI responsibly

**Answer:** D

**Explanation:** ISO/IEC 42001 specifies requirements for establishing and improving an AI management system.

### D5-041
*Multiple Choice | Medium*

**Question:** What is the NIST AI Risk Management Framework (AI RMF) organized around?

- A. Prompting, tuning, serving, billing
- B. Govern, Map, Measure, and Manage functions
- C. Collect, store, delete, archive
- D. Compression, encryption, caching, routing

**Answer:** B

**Explanation:** The AI RMF is a voluntary framework that helps organizations identify and manage AI risks across the lifecycle.

### D5-042
*Multiple Choice | Medium*

**Question:** Which regulation primarily governs the protection of personal data of individuals in the European Union?

- A. GDPR
- B. HIPAA
- C. PCI DSS
- D. SOX

**Answer:** A

**Explanation:** The General Data Protection Regulation sets rules for processing personal data, including consent, purpose limitation, and data subject rights.

### D5-043
*Multiple Choice | Medium*

**Question:** Which U.S. regulation protects individually identifiable health information handled by covered entities and business associates?

- A. HIPAA
- B. PCI DSS
- C. GDPR
- D. FERPA

**Answer:** A

**Explanation:** HIPAA governs protected health information. AWS offers HIPAA-eligible services, and customers must sign a business associate addendum and configure services appropriately.

### D5-044
*Multiple Choice | Medium*

**Question:** Which is a regulatory compliance challenge specific to generative AI?

- A. High disk speed
- B. Too many GPUs
- C. Rapidly evolving regulations, algorithm accountability, transparency, bias, and privacy requirements
- D. Lack of internet

**Answer:** C

**Explanation:** Generative AI raises new questions about explainability, data usage, and liability, and laws are still developing.

### D5-045
*Multiple Choice | Medium*

**Question:** How can a customer obtain a business associate addendum (BAA) and download AWS compliance reports?

- A. Through AWS Artifact
- B. By contacting a Region
- C. By email to a random address
- D. Through AWS Shield

**Answer:** A

**Explanation:** Artifact provides access to compliance documents and lets customers review and accept agreements.

### D5-046
*Multiple Choice | Medium*

**Question:** Which statement about Amazon Bedrock and compliance is accurate?

- A. Bedrock is in scope for several compliance standards, but customers remain responsible for configuring their use to meet their own requirements
- B. Bedrock removes all customer compliance duties
- C. Bedrock requires public internet
- D. Bedrock is not covered by any compliance programs

**Answer:** A

**Explanation:** AWS publishes which services are in scope for programs such as SOC, ISO, and HIPAA eligibility. Compliance remains a shared effort.

### D5-047
*Multiple Choice | Medium*

**Question:** Which elements are part of an AI governance strategy?

- A. Only marketing plans
- B. Policies, review cadence and strategies, transparency standards, and team training
- C. Only hardware purchases
- D. Only code style

**Answer:** B

**Explanation:** Governance establishes the rules, oversight, and education needed to manage AI risks consistently.

### D5-048
*Multiple Choice | Medium*

**Question:** What is the role of an AI governance committee or board?

- A. To train models
- B. To oversee AI policies, risk assessments, approvals, and accountability across the organization
- C. To write all code
- D. To manage billing

**Answer:** B

**Explanation:** A cross-functional body, including legal, security, data, and business roles, sets standards and reviews high-risk use cases.

### D5-049
*Multiple Choice | Medium*

**Question:** Why must organizations train teams on AI policies and responsible use?

- A. It reduces model size
- B. It replaces audits
- C. Staff need to understand risks, policies, and their responsibilities so that practices are followed consistently
- D. It improves GPU speed

**Answer:** C

**Explanation:** Training turns policy into practice and reduces mistakes such as pasting confidential data into unapproved tools.

### D5-050
*Multiple Choice | Medium*

**Question:** Which activities are typical data governance strategies for AI?

- A. Allowing unlogged access
- B. Random deletion
- C. Ignoring lifecycle
- D. Managing the data lifecycle, logging, residency, monitoring, observation, and retention

**Answer:** D

**Explanation:** Defined policies and controls over how data is collected, stored, used, monitored, and deleted underpin trustworthy AI.

### D5-051
*Multiple Choice | Medium*

**Question:** What is the purpose of defining a regular review cadence for AI systems and policies?

- A. To avoid documentation
- B. To periodically reassess risks, performance, and compliance as models, data, and regulations change
- C. To reduce logging
- D. To increase token usage

**Answer:** B

**Explanation:** Regular reviews keep controls effective and catch drift, new threats, and regulatory updates.

### D5-052
*Multiple Choice | Medium*

**Question:** How can resource tagging support AI governance?

- A. It prevents all access
- B. It encrypts data
- C. It helps organize, track ownership, enforce policies, and allocate costs for AI resources
- D. It speeds up inference

**Answer:** C

**Explanation:** Consistent tags identify owners, environments, and data sensitivity, and they can be used with tag policies and IAM conditions.

### D5-053
*Multiple Choice | Medium*

**Question:** What is the best practice for the IAM role used by an action group's Lambda function in a Bedrock agent?

- A. Share the same role with all functions
- B. Disable the role
- C. Grant only the specific permissions needed for the actions it performs
- D. Grant it full administrator access

**Answer:** C

**Explanation:** Agents can act on systems, so each function needs narrowly scoped permissions to limit impact if the agent is manipulated.

### D5-054
*Multiple Choice | Medium*

**Question:** Which approach provides defense in depth against prompt injection?

- A. Layering input validation, clear instruction separation, Guardrails, output validation, and least-privilege tool access
- B. Trusting users
- C. Hiding the prompt only
- D. Relying on a single filter

**Answer:** A

**Explanation:** No single control is sufficient, so multiple layers reduce both likelihood and impact.

### D5-055
*Multiple Choice | Medium*

**Question:** How can a RAG application ensure users only see answers derived from documents they are authorized to access?

- A. Rely on the model to decide
- B. Ignore permissions
- C. Enforce access controls at retrieval, for example through metadata filtering and permission-aware connectors
- D. Make all documents public

**Answer:** C

**Explanation:** Authorization must be applied before content reaches the prompt. Amazon Q Business, for example, honors source access controls.

### D5-056
*Multiple Choice | Medium*

**Question:** Why should vector stores that hold embeddings of sensitive documents be secured?

- A. Vectors are always public
- B. Embeddings can leak information about the source content, so they need encryption and access controls
- C. Security is unnecessary for vectors
- D. Embeddings contain no information

**Answer:** B

**Explanation:** Embeddings are derived from original content and may be inverted or queried to reveal sensitive information.

### D5-057
*Multiple Choice | Medium*

**Question:** Why is it important to protect model invocation logs?

- A. They may contain sensitive prompts and responses, so they require encryption and restricted access
- B. They have no value
- C. They are always empty
- D. They are public

**Answer:** A

**Explanation:** Logs help audits but can themselves become a data exposure risk if not secured and retained appropriately.

### D5-058
*Multiple Choice | Medium*

**Question:** Why does AWS Region selection matter for generative AI workloads from a governance perspective?

- A. It determines where data is processed and stored, which affects residency, latency, and available models and features
- B. It changes the prompt
- C. It has no effect
- D. It changes the model's vocabulary

**Answer:** A

**Explanation:** Regional choices help meet sovereignty requirements and constrain where data flows, including when using cross-Region inference.

### D5-059
*Multiple Choice | Medium*

**Question:** What is the difference between anonymization and pseudonymization?

- A. Anonymization irreversibly removes the ability to identify individuals, while pseudonymization replaces identifiers but may allow re-identification with additional data
- B. Anonymization is always reversible
- C. Pseudonymization irreversibly removes identifiers
- D. They are identical

**Answer:** A

**Explanation:** Regulations like GDPR treat them differently. Truly anonymous data falls outside many privacy rules, while pseudonymized data is still personal data.

### D5-060
*Multiple Choice | Medium*

**Question:** Which dimension of data quality is checked when verifying that values are complete, accurate, and consistent?

- A. Data compression
- B. Data quality assessment
- C. Data routing
- D. Data caching

**Answer:** B

**Explanation:** Poor-quality data undermines model performance and trust, so quality checks are part of secure and responsible data engineering.

### D5-061
*Multiple Choice | Medium*

**Question:** How can data integrity be protected during storage and transfer?

- A. By removing logs
- B. By sharing credentials
- C. By using checksums, versioning, and access controls to detect and prevent unauthorized changes
- D. By skipping validation

**Answer:** C

**Explanation:** Integrity controls ensure that data has not been tampered with, which protects against poisoning and corruption.

### D5-062
*Multiple Choice | Medium*

**Question:** Which service helps mitigate distributed denial-of-service (DDoS) attacks on public endpoints?

- A. Amazon Lex
- B. AWS Shield
- C. Amazon Textract
- D. Amazon Polly

**Answer:** B

**Explanation:** AWS Shield provides managed DDoS protection, with Shield Standard enabled by default.

### D5-063
*Multiple Choice | Medium*

**Question:** Which AWS service adds user sign-up, sign-in, and access control to web and mobile applications, such as a generative AI chat front end?

- A. AWS Glue
- B. AWS Shield
- C. Amazon Cognito
- D. Amazon Polly

**Answer:** C

**Explanation:** Cognito provides authentication and authorization for application users, so only approved users can reach AI features.

### D5-064
*Multiple Choice | Medium*

**Question:** Which service provides centralized workforce single sign-on access to multiple AWS accounts and applications?

- A. AWS Glue
- B. AWS IAM Identity Center
- C. Amazon Lex
- D. Amazon Polly

**Answer:** B

**Explanation:** IAM Identity Center simplifies and centralizes access management with SSO and permission sets.

### D5-065
*Multiple Choice | Medium*

**Question:** Which SageMaker network security option helps keep training and inference traffic private?

- A. Using shared credentials
- B. Running jobs and endpoints in a customer VPC with network isolation as needed
- C. Disabling encryption
- D. Making all endpoints public

**Answer:** B

**Explanation:** VPC configuration, endpoints, and network isolation restrict data movement and reduce exposure.

### D5-066
*Multiple Choice | Medium*

**Question:** What does Amazon SageMaker Role Manager help with?

- A. Quickly creating least-privilege IAM roles tailored to ML personas such as data scientists and MLOps engineers
- B. Labeling data
- C. Translating text
- D. Hosting vectors

**Answer:** A

**Explanation:** Role Manager provides templates and guided setup for persona-based permissions.

### D5-067
*Multiple Choice | Medium*

**Question:** Which SageMaker features support model governance?

- A. Spot instances
- B. Model Cards, Model Registry, and Model Dashboard
- C. Neo compilation only
- D. Polly voices

**Answer:** B

**Explanation:** These help document models, control versions and approvals, and monitor model risk across the organization.

### D5-068
*Multiple Choice | Medium*

**Question:** What supply chain risk exists when using third-party models or datasets?

- A. Models or data may contain vulnerabilities, backdoors, or licensing issues, so provenance should be verified and artifacts scanned
- B. Lower latency
- C. Higher accuracy always
- D. No risk

**Answer:** A

**Explanation:** Vet sources, check licenses and integrity, and scan artifacts before use in production.

### D5-069
*Multiple Choice | Medium*

**Question:** Why implement model versioning and approval workflows?

- A. They provide traceability, controlled promotion to production, and the ability to roll back
- B. They speed up GPUs
- C. They remove logging
- D. They compress weights

**Answer:** A

**Explanation:** Registries and approval steps support governance and reproducibility.

### D5-070
*Multiple Choice | Medium*

**Question:** Why are audit trails essential for AI governance?

- A. They remove the need for policy
- B. They reduce cost
- C. They raise accuracy
- D. They provide an immutable record of who did what, supporting accountability, investigations, and compliance

**Answer:** D

**Explanation:** CloudTrail, invocation logs, and registry history let organizations demonstrate control and investigate incidents.

### D5-071
*Multiple Choice | Medium*

**Question:** Which step belongs in an AI incident response plan?

- A. Deleting all logs
- B. Predefined procedures to detect, contain, investigate, and remediate AI-related incidents, such as data leakage or harmful outputs
- C. Waiting for customers to complain
- D. Ignoring the issue

**Answer:** B

**Explanation:** Having runbooks and roles in place shortens response time and reduces harm.

### D5-072
*Multiple Choice | Hard*

**Question:** Auditors ask who invoked which foundation models and when. Which combination best provides this evidence?

- A. Amazon Polly logs
- B. Route 53 query logs only
- C. AWS CloudTrail for API activity and Bedrock model invocation logging for request details
- D. S3 Intelligent-Tiering reports

**Answer:** C

**Explanation:** CloudTrail captures API calls and identities, and invocation logging stores prompts and responses for deeper audits.

### D5-073
*Multiple Choice | Hard*

**Question:** A compliance officer wants to download SOC and ISO reports for AWS services used in an AI solution. Which service should they use?

- A. AWS Config
- B. Amazon GuardDuty
- C. AWS Artifact
- D. Amazon Inspector

**Answer:** C

**Explanation:** Artifact is the self-service portal for AWS compliance reports and agreements.

### D5-074
*Multiple Choice | Hard*

**Question:** A developer should be able to invoke only one approved model in Amazon Bedrock. What is the most appropriate control?

- A. Give the developer AdministratorAccess
- B. An IAM policy allowing InvokeModel only on that model's ARN
- C. Disable CloudTrail
- D. Share the root account

**Answer:** B

**Explanation:** Resource-level permissions enforce least privilege and prevent use of unapproved models.

### D5-075
*Multiple Choice | Hard*

**Question:** A company wants to automatically detect and alert if any S3 bucket holding training data is made public or lacks encryption. Which service is best suited?

- A. AWS Config rules
- B. Amazon Translate
- C. Amazon Lex
- D. Amazon Polly

**Answer:** A

**Explanation:** Config evaluates resource settings against rules and can trigger remediation or notifications when they drift out of compliance.

### D5-076
*Multiple Choice | Hard*

**Question:** An enterprise wants to prevent employees' prompts from exposing credit card numbers or national IDs to a model and from returning them in responses. Which feature should be applied?

- A. Larger context windows
- B. Higher temperature
- C. Amazon Bedrock Guardrails sensitive information filters
- D. Provisioned Throughput

**Answer:** C

**Explanation:** PII filters can detect and mask or block sensitive entities in inputs and outputs.

### D5-077
*Multiple Choice | Hard*

**Question:** A large enterprise wants to prohibit all member accounts from using unapproved AWS Regions or AI services, regardless of local IAM permissions. Which control is best?

- A. IAM user policies in each account only
- B. Amazon Polly
- C. Service control policies in AWS Organizations
- D. Resource tags only

**Answer:** C

**Explanation:** SCPs set organization-wide permission boundaries that local administrators cannot override.

### D5-078
*Multiple Choice | Hard*

**Question:** A security team wants to control encryption keys for AI training data, including rotation and the ability to disable keys. Which approach should they use?

- A. Store keys in plain text
- B. Disable encryption
- C. Customer managed AWS KMS keys with rotation enabled and tightly scoped key policies
- D. Use public keys only

**Answer:** C

**Explanation:** Customer managed keys offer control and auditability, including automatic rotation and the ability to revoke access.

### D5-079
*Multiple Choice | Hard*

**Question:** A regulated company wants to continuously gather evidence to demonstrate that its generative AI controls meet a compliance framework. Which service is designed for this?

- A. Amazon Transcribe
- B. AWS Audit Manager
- C. Amazon Polly
- D. AWS Shield

**Answer:** B

**Explanation:** Audit Manager maps AWS usage to control frameworks and automates evidence collection for audits.

### D5-080
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO AWS services help with logging and monitoring of AI workloads? (Select TWO.)

- A. Amazon CloudWatch
- B. Amazon Polly
- C. Amazon Translate
- D. Amazon Lex
- E. AWS CloudTrail

**Answer:** A, E

**Explanation:** CloudTrail records API activity, and CloudWatch collects metrics, logs, and alarms. The others are AI services, not monitoring tools.

### D5-081
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO practices strengthen data protection for AI workloads? (Select TWO.)

- A. Use TLS to encrypt data in transit
- B. Encrypt data at rest with KMS
- C. Store credentials in code
- D. Make S3 buckets public for convenience
- E. Share one admin account

**Answer:** A, B

**Explanation:** Encryption at rest and in transit are baseline controls. The other options increase risk.

### D5-082
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO actions apply the principle of least privilege? (Select TWO.)

- A. Share access keys among team members
- B. Attach AdministratorAccess to all developers
- C. Grant only the specific actions and resources needed in IAM policies
- D. Use roles with temporary credentials
- E. Disable MFA

**Answer:** C, D

**Explanation:** Narrow permissions and short-lived credentials limit exposure. Broad access and shared keys violate least privilege.

### D5-083
*Multiple Response (Select TWO) | Hard*

**Question:** Which TWO are on the OWASP Top 10 for LLM applications? (Select TWO.)

- A. Large screens
- B. Training data poisoning
- C. Prompt injection
- D. Slow compilation
- E. Cache warmup

**Answer:** B, C

**Explanation:** OWASP lists prompt injection, insecure output handling, training data poisoning, model denial of service, supply chain vulnerabilities, sensitive information disclosure, excessive agency, and others.

### D5-084
*Multiple Response (Select TWO) | Medium*

**Question:** Which TWO are elements of data governance for AI? (Select TWO.)

- A. Deleting audit logs
- B. Ignoring data residency
- C. Defined data retention and lifecycle policies
- D. Logging and monitoring of data access
- E. Unrestricted sharing of datasets

**Answer:** C, D

**Explanation:** Governance includes lifecycle management, monitoring, residency, and access controls, so that data is used appropriately.

### D5-085
*True/False | Medium*

**Question:** Amazon Bedrock uses customers' prompts and completions to train the base foundation models shared with other customers.

- A. True
- B. False

**Answer:** False

**Explanation:** AWS states that Bedrock does not use customer inputs or outputs to train base models or share them with model providers.

### D5-086
*True/False | Medium*

**Question:** AWS CloudTrail can record API calls made to Amazon Bedrock.

- A. True
- B. False

**Answer:** True

**Explanation:** CloudTrail captures management events and supports logging of API activity for auditing and security analysis.

### D5-087
*True/False | Medium*

**Question:** Granting only the permissions required for a task is consistent with the principle of least privilege.

- A. True
- B. False

**Answer:** True

**Explanation:** Minimizing permissions reduces risk and is a foundational security practice.

### D5-088
*True/False | Medium*

**Question:** If data is encrypted, strict access controls are no longer necessary.

- A. True
- B. False

**Answer:** False

**Explanation:** Encryption complements but does not replace authentication, authorization, and monitoring. Authorized principals can still decrypt and misuse data.

### D5-089
*True/False | Medium*

**Question:** Data residency regulations may require that data remain in specific geographic locations.

- A. True
- B. False

**Answer:** True

**Explanation:** Many laws restrict cross-border data transfers, so Region selection and data flow design are governance issues.

### D5-090
*True/False | Medium*

**Question:** Because AWS holds compliance certifications, any workload a customer runs on AWS is automatically compliant.

- A. True
- B. False

**Answer:** False

**Explanation:** Certifications cover AWS's responsibilities. Customers must configure and operate workloads in line with applicable requirements.

### D5-091
*Multiple Choice | Medium*

**Question:** What does defense in depth mean?

- A. Applying multiple layers of security controls so that a failure of one does not compromise the system
- B. Using only perimeter security
- C. Relying on one strong control
- D. Using deep neural networks

**Answer:** A

**Explanation:** Layers such as identity, network, data, application, and monitoring controls together reduce risk.

### D5-092
*Multiple Choice | Medium*

**Question:** Why is data classification a foundational governance activity?

- A. It labels data by sensitivity so appropriate protections, access, and handling rules can be applied
- B. It compresses data
- C. It chooses the model
- D. It speeds up training

**Answer:** A

**Explanation:** You cannot protect or govern data properly if you do not know which data is sensitive or regulated.

### D5-093
*Multiple Choice | Medium*

**Question:** A financial firm is starting a generative AI project. What is an appropriate first compliance step?

- A. Skip legal review
- B. Deploy first and review later
- C. Hide the project from auditors
- D. Identify applicable regulations and internal policies and map them to technical and process controls

**Answer:** D

**Explanation:** Understanding obligations up front lets teams design controls and documentation, rather than retrofitting them.

### D5-094
*Multiple Choice | Medium*

**Question:** What can administrators configure in Amazon Q Business to help control what the assistant can discuss or retrieve?

- A. Nothing
- B. Admin controls and guardrails, such as blocked topics and data source access scoping
- C. Only fonts
- D. Only GPU type

**Answer:** B

**Explanation:** Q Business offers administrative controls and respects source permissions so answers stay within approved topics and authorized content.

### D5-095
*True/False | Easy*

**Question:** Using IAM roles with temporary credentials is generally safer than embedding long-term access keys in application code.

- A. True
- B. False

**Answer:** True

**Explanation:** Temporary credentials expire automatically and are not stored in code, which reduces the risk and impact of credential leakage.

### D5-096
*Multiple Choice | Hard*

**Question:** A team stores Bedrock model invocation logs, containing prompts and responses, in Amazon S3. Which step best reduces the privacy risk of those logs?

- A. Email the logs to all developers
- B. Make the bucket public for easy sharing
- C. Keep the logs forever with open access
- D. Encrypt the logs with a KMS key, restrict access with least-privilege IAM, and apply a retention and lifecycle policy

**Answer:** D

**Explanation:** Logs can contain sensitive data, so they need encryption, tight access control, and defined retention. These steps protect the data while preserving audit value.

---

## Answer Key

### Domain 1: Fundamentals of AI and ML

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|---|---|
| D1-001 | True | D1-002 | D | D1-003 | C | D1-004 | A | D1-005 | A |
| D1-006 | D | D1-007 | D | D1-008 | True | D1-009 | A | D1-010 | B |
| D1-011 | D | D1-012 | B | D1-013 | A | D1-014 | True | D1-015 | C |
| D1-016 | C | D1-017 | A | D1-018 | A | D1-019 | B | D1-020 | B |
| D1-021 | B | D1-022 | D | D1-023 | A | D1-024 | B | D1-025 | B |
| D1-026 | A | D1-027 | C | D1-028 | A | D1-029 | A | D1-030 | C |
| D1-031 | C | D1-032 | B | D1-033 | D | D1-034 | A | D1-035 | C |
| D1-036 | D | D1-037 | C | D1-038 | False | D1-039 | D | D1-040 | B |
| D1-041 | A | D1-042 | B | D1-043 | C | D1-044 | B | D1-045 | B |
| D1-046 | B | D1-047 | D | D1-048 | A | D1-049 | D | D1-050 | D |
| D1-051 | D | D1-052 | B | D1-053 | D | D1-054 | B | D1-055 | B |
| D1-056 | A | D1-057 | C | D1-058 | D | D1-059 | D | D1-060 | A |
| D1-061 | B | D1-062 | C | D1-063 | A | D1-064 | A | D1-065 | D |
| D1-066 | A | D1-067 | D | D1-068 | D | D1-069 | A | D1-070 | B |
| D1-071 | B | D1-072 | B | D1-073 | A | D1-074 | D | D1-075 | D |
| D1-076 | C | D1-077 | B | D1-078 | D | D1-079 | C | D1-080 | B |
| D1-081 | D | D1-082 | C | D1-083 | A | D1-084 | D | D1-085 | A |
| D1-086 | C, E | D1-087 | B | D1-088 | A | D1-089 | False | D1-090 | C, D |
| D1-091 | True | D1-092 | A | D1-093 | False |  |  |  |  |

### Domain 2: Fundamentals of Generative AI

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|---|---|
| D2-001 | True | D2-002 | D | D2-003 | A | D2-004 | D | D2-005 | C |
| D2-006 | B | D2-007 | C | D2-008 | A | D2-009 | D | D2-010 | B |
| D2-011 | C | D2-012 | B | D2-013 | True | D2-014 | C | D2-015 | A |
| D2-016 | B | D2-017 | D | D2-018 | D | D2-019 | B | D2-020 | C |
| D2-021 | False | D2-022 | C | D2-023 | C, E | D2-024 | D | D2-025 | D |
| D2-026 | C | D2-027 | C | D2-028 | D | D2-029 | B | D2-030 | B |
| D2-031 | B | D2-032 | D | D2-033 | B | D2-034 | D | D2-035 | A |
| D2-036 | D | D2-037 | C | D2-038 | B | D2-039 | C | D2-040 | D |
| D2-041 | C | D2-042 | C | D2-043 | C | D2-044 | B | D2-045 | D |
| D2-046 | B | D2-047 | A | D2-048 | C | D2-049 | A | D2-050 | False |
| D2-051 | A | D2-052 | A | D2-053 | B | D2-054 | B | D2-055 | B |
| D2-056 | D | D2-057 | A | D2-058 | A | D2-059 | D | D2-060 | B |
| D2-061 | B | D2-062 | D | D2-063 | True | D2-064 | False | D2-065 | False |
| D2-066 | True | D2-067 | B | D2-068 | A | D2-069 | D | D2-070 | B |
| D2-071 | B | D2-072 | C | D2-073 | C | D2-074 | B | D2-075 | D |
| D2-076 | C | D2-077 | D | D2-078 | A | D2-079 | D | D2-080 | C |
| D2-081 | B | D2-082 | A | D2-083 | C | D2-084 | B | D2-085 | C |
| D2-086 | True | D2-087 | A | D2-088 | False | D2-089 | C | D2-090 | A |

### Domain 3: Applications of Foundation Models

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|---|---|
| D3-001 | D | D3-002 | D | D3-003 | B | D3-004 | A | D3-005 | A |
| D3-006 | B | D3-007 | C | D3-008 | B | D3-009 | D | D3-010 | D |
| D3-011 | A | D3-012 | A | D3-013 | C | D3-014 | B | D3-015 | C |
| D3-016 | C | D3-017 | D | D3-018 | B | D3-019 | B | D3-020 | B |
| D3-021 | C | D3-022 | B | D3-023 | B | D3-024 | A | D3-025 | B |
| D3-026 | A | D3-027 | D | D3-028 | D | D3-029 | C | D3-030 | C |
| D3-031 | C | D3-032 | A | D3-033 | True | D3-034 | C | D3-035 | B |
| D3-036 | B | D3-037 | A | D3-038 | B | D3-039 | C | D3-040 | D |
| D3-041 | D | D3-042 | A | D3-043 | C | D3-044 | A | D3-045 | D |
| D3-046 | C | D3-047 | B | D3-048 | B | D3-049 | B | D3-050 | A |
| D3-051 | C | D3-052 | True | D3-053 | A | D3-054 | D | D3-055 | A |
| D3-056 | C | D3-057 | A | D3-058 | C | D3-059 | D | D3-060 | A |
| D3-061 | A | D3-062 | A | D3-063 | D | D3-064 | A | D3-065 | A |
| D3-066 | C | D3-067 | D | D3-068 | A | D3-069 | B | D3-070 | D |
| D3-071 | C | D3-072 | A | D3-073 | B | D3-074 | A | D3-075 | A, E |
| D3-076 | A, B | D3-077 | D, E | D3-078 | A, C | D3-079 | False | D3-080 | True |
| D3-081 | False | D3-082 | False | D3-083 | A | D3-084 | B | D3-085 | C |
| D3-086 | D | D3-087 | C | D3-088 | A | D3-089 | D | D3-090 | B |
| D3-091 | B | D3-092 | True | D3-093 | A | D3-094 | C | D3-095 | False |
| D3-096 | True |  |  |  |  |  |  |  |  |

### Domain 4: Guidelines for Responsible AI

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|---|---|
| D4-001 | C | D4-002 | B | D4-003 | D | D4-004 | A | D4-005 | C |
| D4-006 | D | D4-007 | C | D4-008 | D | D4-009 | D | D4-010 | C |
| D4-011 | D | D4-012 | D | D4-013 | A | D4-014 | B | D4-015 | D |
| D4-016 | D | D4-017 | A | D4-018 | C | D4-019 | C | D4-020 | A |
| D4-021 | A | D4-022 | D | D4-023 | D | D4-024 | D | D4-025 | D |
| D4-026 | A | D4-027 | A | D4-028 | B | D4-029 | B | D4-030 | C |
| D4-031 | B | D4-032 | A | D4-033 | C | D4-034 | B | D4-035 | A |
| D4-036 | B | D4-037 | D | D4-038 | D | D4-039 | C | D4-040 | D |
| D4-041 | B | D4-042 | A | D4-043 | D | D4-044 | A | D4-045 | B |
| D4-046 | A | D4-047 | D | D4-048 | B | D4-049 | C | D4-050 | C |
| D4-051 | B | D4-052 | A | D4-053 | C | D4-054 | True | D4-055 | False |
| D4-056 | True | D4-057 | False | D4-058 | A, D | D4-059 | A, B | D4-060 | B, E |
| D4-061 | C | D4-062 | A | D4-063 | D | D4-064 | C | D4-065 | A |
| D4-066 | C | D4-067 | D | D4-068 | A | D4-069 | B | D4-070 | D |
| D4-071 | B | D4-072 | D | D4-073 | A | D4-074 | D | D4-075 | D |
| D4-076 | C | D4-077 | B | D4-078 | C | D4-079 | A | D4-080 | D |
| D4-081 | D | D4-082 | D | D4-083 | D | D4-084 | C | D4-085 | A |
| D4-086 | B | D4-087 | A | D4-088 | D | D4-089 | B | D4-090 | D |
| D4-091 | C | D4-092 | C | D4-093 | B | D4-094 | True | D4-095 | True |
| D4-096 | A | D4-097 | C | D4-098 | False |  |  |  |  |

### Domain 5: Security, Compliance, and Governance

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|---|---|
| D5-001 | B | D5-002 | C | D5-003 | B | D5-004 | B | D5-005 | B |
| D5-006 | A | D5-007 | B | D5-008 | A | D5-009 | D | D5-010 | D |
| D5-011 | B | D5-012 | A | D5-013 | B | D5-014 | C | D5-015 | C |
| D5-016 | A | D5-017 | D | D5-018 | A | D5-019 | A | D5-020 | A |
| D5-021 | B | D5-022 | A | D5-023 | C | D5-024 | B | D5-025 | B |
| D5-026 | D | D5-027 | D | D5-028 | D | D5-029 | D | D5-030 | C |
| D5-031 | C | D5-032 | B | D5-033 | D | D5-034 | D | D5-035 | D |
| D5-036 | C | D5-037 | B | D5-038 | B | D5-039 | C | D5-040 | D |
| D5-041 | B | D5-042 | A | D5-043 | A | D5-044 | C | D5-045 | A |
| D5-046 | A | D5-047 | B | D5-048 | B | D5-049 | C | D5-050 | D |
| D5-051 | B | D5-052 | C | D5-053 | C | D5-054 | A | D5-055 | C |
| D5-056 | B | D5-057 | A | D5-058 | A | D5-059 | A | D5-060 | B |
| D5-061 | C | D5-062 | B | D5-063 | C | D5-064 | B | D5-065 | B |
| D5-066 | A | D5-067 | B | D5-068 | A | D5-069 | A | D5-070 | D |
| D5-071 | B | D5-072 | C | D5-073 | C | D5-074 | B | D5-075 | A |
| D5-076 | C | D5-077 | C | D5-078 | C | D5-079 | B | D5-080 | A, E |
| D5-081 | A, B | D5-082 | C, D | D5-083 | B, C | D5-084 | C, D | D5-085 | False |
| D5-086 | True | D5-087 | True | D5-088 | False | D5-089 | True | D5-090 | False |
| D5-091 | A | D5-092 | A | D5-093 | D | D5-094 | B | D5-095 | True |
| D5-096 | D |  |  |  |  |  |  |  |  |
