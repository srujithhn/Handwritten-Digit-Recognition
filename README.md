# Handwritten Digit Recognition (LeNet-5 style CNN)

A convolutional neural network that reads handwritten digits (0 to 9) from the MNIST dataset.

**Result: 98.73% accuracy on the 10,000-image MNIST test set.**

## What I did

- **Data:** MNIST, 60,000 training images, with 20% held out for validation, plus the separate 10,000-image test set.
- **Prep:** reshaped images to 28 x 28 x 1, normalised pixel values, and one-hot encoded the 10 labels.
- **Model:** a LeNet-5 style network: three convolution layers with tanh activation and average pooling, then dense layers. 303,626 trainable parameters.
- **Training:** Adam optimiser, categorical cross-entropy loss, batch size 32, 20 epochs.

## What I'd do differently now

- Normalise the validation and test sets with the training set's mean and standard deviation. I normalised each split with its own statistics, which slightly leaks information about the test data.
- Add a confusion matrix to see which digits get mixed up (for example 4 vs 9), not just one accuracy number.
- Save the trained model so it can be reused without retraining.

## Run it

Open `Handwritten.ipynb` in Jupyter or Google Colab. It needs TensorFlow/Keras, scikit-learn, NumPy and pandas; MNIST downloads automatically.

Built by [Srujith H N](https://www.linkedin.com/in/srujith-h-n-b7b000267). My current work: [DocAgent Lite](https://github.com/srujithhn/docagent-lite).
