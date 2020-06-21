# TensorPlot
#### Easily plot keras models using nice style and formatting
author: Manu Blanco Valentin </br>
github: [manuelblancovalentin](http://github.com/manuelblancovalentin) </br>
version: v0.0.1


## What is this module intended for?

TODO 


## How to install?

To start using tensorplot simply install it via pip using the following command:

```bash
pip install TensorPlot
```

Extra documentation about the module can be found in our pypi page:

https://pypi.org/project/TensorPlot/


Take a look at this demo snippet:

```python
""" Import tensorflow and tensorplot """
import tensorflow as tf
import tensorplot as tp

""" Define model """
model = tf.keras.Sequential()
model.add(tf.keras.layers.Input(shape=(1,128,128)))
model.add(tf.keras.layers.Conv2D(32,3,data_format='channels_first'))
model.add(tf.keras.layers.BatchNormalization(axis=1))
model.add(tf.keras.layers.ReLU())
model.add(tf.keras.layers.Dropout(.5))
model.add(tf.keras.layers.MaxPool2D(2,data_format='channels_first'))
model.add(tf.keras.layers.Conv2D(64,3,data_format='channels_first'))
model.add(tf.keras.layers.BatchNormalization(axis=1))
model.add(tf.keras.layers.ReLU())
model.add(tf.keras.layers.Dropout(.5))
model.add(tf.keras.layers.MaxPool2D(2,data_format='channels_first'))
model.add(tf.keras.layers.Conv2D(128,3,strides=1, padding = 'same', data_format='channels_first'))
model.add(tf.keras.layers.BatchNormalization(axis=1))
model.add(tf.keras.layers.ReLU())
model.add(tf.keras.layers.Dropout(.5))
model.add(tf.keras.layers.Conv2D(128,3,strides=2,data_format='channels_first'))
model.add(tf.keras.layers.BatchNormalization(axis=1))
model.add(tf.keras.layers.ReLU())
model.add(tf.keras.layers.Dropout(.5))
model.add(tf.keras.layers.Flatten())
model.add(tf.keras.layers.Dense(64))
model.add(tf.keras.layers.ReLU())
model.add(tf.keras.layers.Dense(1, name = 'output_A'))

""" Generate graph """
tp.plot_model(model, filename = 'model.png')

```

## How to cite this work?

Please, if you found my work valuable and it was useful for you, consider citing it in any published work that used it to help me improve the visibility of my code and make it easier for other people to access it. 

If so, use the following bibtex entry in your paper:

```
@misc{MBValentin2020TensorPlot,
  author = {Valentin, Manuel Blanco},
  title = {Tensorplot},
  year = {2020},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/manuelblancovalentin/tensorplot}}
}
```
