# dpn

Deep Predictive Coding Networks Demo
Taichi Iki, 2016-06-17

**Paper Reference:**
**"Deep Predictive Coding Networks for Video Prediction and Unsupervised Learning"**
William Lotter, Gabriel Kreiman, David Cox
[https://arxiv.org/abs/1605.08104](https://arxiv.org/abs/1605.08104)

---

This is a sample implementation just to try running it for now.
I gave up on modeling with Keras or Chainer and implemented it using Theano instead.
It’s quite messy.

### Note

At this stage, the full pipeline of training and prediction runs *without errors*,
but there hasn’t yet been a successful example of effective learning.
Still, I hope it can serve as a topic of interest or a useful reference.
Also, if anyone understands why the learning isn't working well, please do reach out.

---

## Dependencies

* Theano
* PIL (Python Imaging Library)

---

## `dpn_learn.py`

* Trains the model on image data.
* Training samples should be placed in a directory named `sample`, sequentially numbered (e.g., `0.png`, `1.png`, `2.png`, etc.).
* Files are sorted numerically and grouped by timestep to form sequences.
* For other settings, refer to the section below `if __name__ == '__main__':`
* Model construction takes quite a bit of time, so be patient.
* As training progresses, files like `****.pkl` and `****.npz` will be generated. These are the trained models.

---

## `dpn_eval.py`

* Loads a trained model using `load`.
* Applies the model to images using `applyimg(imagepath or matrixdata)`.
* `matrixdata` should be a 3D array of the format `[channel, height, width]`.
* Each pixel value must be normalized to the range `0.0 – 1.0`.

---

Let me know if you want help rewriting or modernizing this Theano code to use PyTorch or TensorFlow.
