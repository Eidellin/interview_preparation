# Binary Classification Task
= binomial classification task

We always want to classify the date of a given set into two groups.

We usually define one of the classes as + and one as -.

  * Sometimes _the classes are equally important_ (e.g. recognition of dog vs cat in image classification)
  * Sometimes __misclassifcation in one__ of the classes is **more costly** than __misclassification in the other class__
    
    (e.g. predicting that someone has cancer while (s)he doesn't have vs predicting that someone doesn't have cancer while (s)he has)

    THERFORE we may prefer to have a better classification in one class at the cost of more errors in the other class.

# Evaluation of Error
If we have a binary classification, then we have two classes of

$y \in {0, 1}$, where we call the calss $y = 1$, + class and

$y = 0$, - class.

### Some evaluation metrics:

  o **True positive:** number of instances from class one that have been predicted as one

  o **True negative:** number of instances from class zero that have been predicted as zero

  o **False positive:** number of instances from class zero that have been predicted as one

  o **False negative:** number of instances from class one that have been predicted as zero

## Contingency Table (= Confusion Matrix)
For two-class prediction case:
![image](https://github.com/Eidellin/interview_preparation/assets/83224546/b38e9031-34d0-4604-860e-aeb3ca5635c2)

## Classification Accuracy
Classification Accuracy on **a sample of labeled pairs** $(x, c(x))$ 

given a learned classification model that predicts, for each instance $x$, a class value,

for each instance $x$, a class value $\hat{c}(x)$:

$$ acc = \frac{1}{|Test|} \sum_{x \in Test} I[\hat{c}(x) = c(x)$$

where $Test$ := a test set
  $I[]$ := the indicator function
  $1 \iff$ its argument evaluates to __true__
  $0$ otherwise.

$$Classification \ Error \ is = 1 - acc$$

## Precision
