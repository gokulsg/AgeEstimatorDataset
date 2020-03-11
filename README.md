# Age Estimator Dataset

This is a submodule providing all necessary data and helper scripts for [Age Estimator](https://github.com/oopDaniel/AgeEstimator).

## Decompress the raw data

> Raw images

To unzip the raw images, run the following script:

`cat dataset.tar.* | tar -xzvf -`

> Extracted Features

`cat features-train-worker0.npy.tar.* | tar -xzvf -`
`cat features-test-worker0.npy.tar.* | tar -xzvf -`

## Get Started

### Load data into Python

In your model, do

```python
from server.data.dataset import DataLoader

dl = DataLoader()
x_train, y_train = dl.load_train()
x_test, y_test = dl.load_test()
```

to start playing with the data.

_Note: the training data are strings of file name, so you'll still need to load the file as matrix to perform any scientific computation._

### Load image by file name

There are several ways to load an image. One way is use `matplotlib`:

```python
import matplotlib.image as img

image = img.imread(x_train[0])
```

### Load features

In your model, do

```python
from server.data.dataset import DataLoader

dl = DataLoader()
x_train, y_train = dl.load_train(feature=True)
x_test, y_test = dl.load_test(feature=True)
```
