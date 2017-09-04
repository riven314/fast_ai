## Tips:

* If accuracy > validation accuracy -> overfitting
* If accuracy < validation accuracy (or both low) -> underfitting
* Do not decrease neural network size (less layers, parameters, etc.) if problems with overfitting. Rather use as big of a neural network as your computational budget allows, and use other regularization techniques to control overfitting, such as dropout, input noise, etc.
* First model should try to overfit before you start worrying about how to handle that - there's no point even thinking about regularization, data augmentation, etc. if you are still under-fitting!
* For standard photos, you normally do not retrain convolutional layers. However, if your problem set contains line art, medical photos and other
* As well as looking at the overall metrics, it's also a good idea to look at examples of each of:
  *. A few correct labels at random
  *. A few incorrect labels at random
  *. The most correct labels of each class (ie. those with highest probability that are correct)
  *. The most incorrect labels of each class (ie. those with highest probability that are incorrect)
  *. The most uncertain labels (ie. those with probability closes to 0.5)


## FAQ:

- **What is an `epoch`?** It is one full pass through training data.
- **What is `relu`?** f(x)=max(0,x) aka. simple threshold at zero. Normally used in intermediate layer.
- **What is `softmax`?** Push values to either 0 or 1. Normally used as last (output) layer.
- **What is `batchnorm`?** Force all inputs to the same scale by subtracting mean and dividing by standard deviation. Up to 10x performance increase.

- **What are `*.npy` files?** Numpy array, saved to a file. [More](https://stackoverflow.com/questions/4090080/what-is-the-way-data-is-stored-in-npy).
- **Why twice bigger batch size for validation?** No backprop, so less memory consumption, so can be bigger.

- ** Why do I get `RuntimeError: You must compile your model before using it.`?** You are missing `model.compile` line.


## TODO

- run Lesson 2 on Horus


## PBs

Personal Bests, only those with `val_acc` > `acc` count:

* catsdogs, lesson 1, stock Vgg16, 2 epochs: 0.9880


## Common iPython Notebooks keyboard shortcuts:

- **Ctrl-m a** -- insert cell above
- **Ctrl-m b** -- insert cell below
- **Ctrl-m m** -- convert to Markdown cell
- **Ctrl-m dd** -- remove cell
