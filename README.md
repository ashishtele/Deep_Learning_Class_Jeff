# Deep Learning Class

- Scripts from Deep Learning class
- Regression using keras
- Classification iris: accuracy, log loss, earlystoping, modelcheckpoint
- Regression mpg: RMSE, modelcheckpoint, kfold
- Binary classification - Breast Cancer data
- Regression with lift curve
- L1 and L2 regularization
- Basic LSTM program
- Sunsplot (LSTM) using keras.

`Question:` Why does Mini-batch gradient descent work?

`Answer:` The examples in the training data are correlated. To see this, consider the extreme case where all 1.2 million images in ILSVRC are in fact made up of exact duplicates of only 1000 unique images (one for each class, or in other words 1200 identical copies of each image). Then it is clear that the gradients we would compute for all 1200 identical copies would all be the same, and when we average the data loss over all 1.2 million images we would get the exact same loss as if we only evaluated on a small subset of 1000. **In practice of course, the dataset would not contain duplicate images, the gradient from a mini-batch is a good approximation of the gradient of the full objective**. Therefore, much faster convergence can be achieved in practice by evaluating the mini-batch gradients to perform more frequent parameter updates

`Question:` Mini-batch as powers of 2?

`Answer:` Many vectorized operation implementations work faster when their inputs are sized in powers of 2. Mini-batch is a hyperparameter but it is not very common to cross-validate it. It is usually based on memory constraints (if any), or set to some value, e.g. 32, 64 or 128.

`Question:` What are the drawbacks of Sigmoid activation function?

`Answer:` 1. Sigmoids saturate and kill gradients. If the initial weights are too large then most neurons would become saturated and the network will barely learn.
          2. Sigmoid outputs are not zero-centered. This could introduce undesirable zig-zagging dynamics in the gradient updates for the weigthts. 
