# Generalization
a key objective of ML

What we are really interested in = generalizing from the **sample of data in** our **training set**.

In ML, generalization = how well a trained model can classify or forecast unseen data.

Training a generalized ML model = in general, it works for $\forall$ subset of unseen data.

Example: when we train a model to classify between dogs and cats.

If the model is provided with **dogs** images dataset **with only two breeds**, it may obtain a good performance. **BUT**, it possibly gets a <u>low classification score when it is tested by other breeds of dogs</u> as well.

There are three basic assumptions for generalization:
- Examples are drawn <u>independently and identically</u> **(i.i.d)** at random at the distribution;
- The distribution is stationary; that is the distribution doesn't change within the data set;
- We always pull from the same distribution (for training, validation, and test samples)

  In practice, we sometimes violate these assumptions.
