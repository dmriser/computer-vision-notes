# Computer Vision Notes (Last Update: 04/29/2020)
These are my scribbles to myself, you're welcome to read them.

## Preprocessing
In addition to loading an image `tensorflow.keras.preprocessing.image.load_image` does two additional operations that are important.
- The image can be resized by using the `target_size` keyword.  The methodology for doing so is set with the `interpolation` keyword.  These methods come from `PIL.image` and default is `PIL.image.NEAREST`.  Here is what I found on a few of the methods.
  - `nearest`: Pick one nearest pixel from the input image, all other pixels are ignored.
  - `bilinear`: Linear interpolation over 2x2 region
  - `bicubic`: Cubic interpolation over 4x4 region
  - `lanczos`:Use a high-quality Lanczos (truncated sinc) filter.  This filter produces high quality results, but is slow.
- The image can be converted to 3 channels from greyscale.

## Architectures
Some notable CNN configurations and interesting layers.

### AlexNet
Winner of the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2012.  Created by Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton.  The full architecture is described in (https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)[their paper].

- After their crushing victory in 2012 almost all ILSVRC submissions have used deep convolutional neural networks.
- Achieved 15.3% top-5 error rate
- Used dropout in the two fully connected (FC) layers to reduce overfitting
- Used image augmentation (crops, flips, brightness scaling) to reduce overfitting
- Encouraged filters to learn diverse feature extractions by using local response normalization.  This technique (google the equation) reduces the output activation if other filter activations at the same spatial position are large.  Local response normalization is applied after the ReLU.
- They used ReLU activation functions.
