# Cross-Validation
= out-of-sample testing

### Cross-validation helps in:
- **Reducing Bias**: Using different subsets of the data for training and testing, reduces the risk of the model being biased toward a specific subset of the data.
- **Estimating the Skill of the Model**: It provides a better estimate of the model's performance on an independent dataset.
- **Model Tuning**: It can be used to tune model parameters for better performance.

**However**, cross-validation can be computationally expensive, especially with large datasets and complex models, as it requires multiple rounds of training and validation.

#### a validation technique to assess 
- the **results of a model to an independent data set**
- the **generalizability of a model**.

#### It involves **partitioning the data** into _multiple sets_

=> systematically **testing the model on one set** WHILE **training** it on **the others**.

#### This process helps in **evaluating** 

**how well a model performs** on an independent dataset

and in **mitigating problems** like overfitting.

### 1. Holdout Method:
   ![image](https://github.com/Eidellin/interview_preparation/assets/83224546/ec654221-0463-4d0f-9cf5-833e11325683)

**Description**: The dataset is divied into two subsets: the **training set** and the **test set**.

The model is _trained on_ the _training set_ => _tested on_ the _test set_.

**Usage**: Typically used when there is a **large amount of data**, ensuring that both sets are large enough to be statistically representative of the problem.

**Pros**:
- **Simple and fast** - especially suitable for large datasets
- **Less computationally expensive**

**Cons**: 
- The **evaluation** may **depend heavily on how the data is divided**;

  Certain random splits can lead to better OR worse performance.

- The model is only **trained** and **tested** **ONCE**, which may NOT provide a robust estimate of its performance.

### 2. Leave-One-Out Cross Validation (LOOCV):
   ![image](https://github.com/Eidellin/interview_preparation/assets/83224546/f054299c-1ef9-44bb-b903-360eba13e243)

**Description**: The dataset is split such that **one sample"** is used as the **test set** and the _rest_ as the __training set__.

This process is **repeated** for each sample in the dataset.

**Usage**: Often used for **small datasets** where maximizing the amount of training data is crucial.

**Pros**:
- Provides a **nearly unbiased estimate** of the **model performance**.
- Every data point is used for both training and testing, which is efficient in terms of data usage.

**Cons**:
- Very **computationally intensive**, especially for large datasets,

BECAUSE the model needs to be **trained** on $N - 1$ samples and tested on 1 sample $N$ times

where $N$ = # samples

- **High variance** in the **testing model's effectiveness**

due to the **high dependence** on a **single data point** for each iteration.

### 3. K-fold Cross Validation
   ![image](https://github.com/Eidellin/interview_preparation/assets/83224546/d09a1f4d-9c9c-4f6a-836d-ff482c892a9e)

**Description**: The dataset is **divided** into **$k$ equal-sized folds**. 

The model is trained on $k - 1$ folds

AND tested on the remaining fold.

This process is repeated $k$ times, with each fold used exactly once as the test set.

**Usage**: Widely used for both small and large datasets.

It provides a good balance between computational efficiency and evaluation robustness.

**Pros**:
- **Every data point** gets to be in **a test set exactly once** and in a **training set** $k - 1$ times,

ENSURING **$\forall$ data** contributes to **both training and evaluation**.

**Cons**:
- **The choice of $k$ can affect the results**; a larger $k$ means more training, which can be more computationally expensive.

#### There are **certain parameters** that need to be **estimated during learning**. 
We use the data, but NOT the __training set__ OR the __test set__.

Instead, we use __validation set__ (= __development set__)

#### Validation Set:
To make the **hyperparameter tuning** and **model selection** independent from the test set, we define another set within the train set.

![image](https://github.com/Eidellin/interview_preparation/assets/83224546/65a3019f-3fc3-45c7-b40b-54999199687b)

### Here's a more detailed breakdown of how cross-validation typically works:

1. **Data Splitting**: The data set is divided into \(k\) smaller sets (or 'folds'). The typical value for \(k\) is 5 or 10, but it can be any number.

2. **Model Training and Validation**: For each of the \(k\) folds:
   - The model is trained on \(k-1\) folds of the data.
   - The remaining part of the data (i.e., the one fold) is used as a test set to validate the model. This test set acts as unseen data for the model.

3. **Performance Measurement**: The performance of the model is measured on each of the \(k\) test sets. Common performance metrics include accuracy, precision, recall, F1 score, etc., depending on the nature of the problem (classification, regression, etc.).

4. **Average Performance**: The average of the performance measurements from each of the \(k\) iterations is taken. This average is considered the overall performance metric of the model.
