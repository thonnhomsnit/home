# Python
-[Download Anaconda](#download-Anaconda)

-[Setting an environment](#setting-an-environment)

-[Original script](#original-script)


## Download Anaconda
Anaconda is the platform that has a lot of tools including Spyder IDE which will be the main IDE that we will use.
To install Anaconda, you need to download from the [link](https://www.anaconda.com/download). The installation process is very straightforward.

## Setting an environment
Before coding, you must setup and install some libraries into your environment because the python script will use several libraries as shown below.

```markdown
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import MinMaxScaler, StandardScaler
import keras
import tensorflow as tf
from keras import backend
from keras.layers import Dropout
from keras.models import Sequential 
from keras.layers import Dense, LSTM, Flatten
```
For example, if you would like to install 'numpy' package, you need to find the available packgage in https://anaconda.org/anaconda/repo and install by using this script.

```markdown
conda install {package name}
```

![alt text for screen readers](interface.png "interface")

## Original script

```markdown
# Define the model
model = Sequential()
model.add(LSTM(units=50, activation='relu', return_sequences=True, input_shape=(2, 6)))
model.add(LSTM(units=25, activation="relu"))
model.add(Dense(units=25))
model.add(Dense(units=4))
model.add(Dense(units=2, activation='tanh'))

# Compile the model
model.compile(loss='mean_squared_error', optimizer='adam', metrics=['accuracy'])

# Print a summary of the model
model.summary()

# Train the model
model.fit(X_data, Y_data, epochs=100, verbose=1, batch_size=32)
```

## lstm_all_rulu.h5

```markdown
# Define the model
model = Sequential()
model.add(LSTM(units=50, activation='relu', return_sequences=True, input_shape=(2, 6)))
model.add(LSTM(units=25, activation="relu"))
model.add(Dense(units=25))
model.add(Dense(units=4))
model.add(Dense(units=2, activation='relu'))

# Compile the model
model.compile(loss='mean_squared_error', optimizer='adam', metrics=['accuracy'])

# Print a summary of the model
model.summary()

# Train the model
model.fit(X_data, Y_data, epochs=100, verbose=1, batch_size=32)
```
