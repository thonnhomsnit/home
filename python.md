# Python Installation
-[Download Anaconda](#Download-Anaconda)

-[Setting an environment](#Setting-an-environment)

-[Common problems](#common-problems)


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
## Common problems
