# Assignment 4 FIT5047

Sample implementation of Elastic Weight Consolidation, a regularization technique for reducing "catastrophic forgetting" when training a neural network sequentially on multiple tasks.

Model Setup: A simple neural network (SimpleNN) with two fully connected layers.

EWC Preparation: The EWC class computes the Fisher Information Matrix (FIM) on the initial task (MNIST) to identify critical parameters. This FIM estimates how important each parameter is for the initial task, preserving these parameters to reduce interference when learning the next task.

**Training without EWC:**

First, the model is trained on MNIST, achieving high accuracy on that task.
Next, the model is trained on Fashion-MNIST without EWC, leading to a drop in accuracy on MNIST due to catastrophic forgetting.

**Training with EWC:**

The model is reset and retrained on MNIST, followed by Fashion-MNIST, using the EWC regularization penalty.


**Results Comparison:**

-Without EWC, MNIST accuracy decreases significantly.

-With EWC, the retained accuracy on MNIST is higher, indicating that EWC helps retain performance on previous tasks while learning new tasks.


## Reference
[Paper](https://www.pnas.org/doi/10.1073/pnas.1611835114)
