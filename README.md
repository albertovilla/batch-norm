# batch-norm
Adding Batch Normalization Layers to a PyTorch Model

To add batch normalization layers to a PyTorch model:

- You add batch normalization to layers inside the__init__ function.
- Layers with batch normalization do not include a bias term. So, for linear or convolutional layers, you'll need to set bias=False if you plan to add batch normalization on the outputs.
- You can use PyTorch's [BatchNorm1d] function to handle the math on linear outputs or [BatchNorm2d] for 2D outputs, like filtered images from convolutional layers.
- You add the batch normalization layer before calling the activation function, so it always goes layer > batch norm > activation.

Finally, when you tested your model, you set it to .eval() mode, which ensures that the batch normalization layers use the populationrather than the batch mean and variance (as they do during training).