# Computer Vision Notes (Last Update: 04/29/2020)

### Preprocessing
In addition to loading an image `tensorflow.keras.preprocessing.image.load_image` does two additional operations that are important.
- The image can be resized by using the `target_size` keyword.  The methodology for doing so is set with the `interpolation` keyword.  These methods come from `PIL.image` and default is `PIL.image.NEAREST`.  Here is what I found on a few of the methods.
  - `nearest`: Pick one nearest pixel from the input image, all other pixels are ignored.
  - `bilinear`: Linear interpolation over 2x2 region
  - `bicubic`: Cubic interpolation over 4x4 region
  - `lanczos`:Use a high-quality Lanczos (truncated sinc) filter.  This filter produces high quality results, but is slow.
- The image can be converted to 3 channels from greyscale.

### Architectures
Something here.

