# LLNet: Low-light Image Enhancement with Deep Learning #

This repository includes the codes and modules used for running LLNet via a Graphical User Interface. Users can choose to train the network from scratch, or to enhance multiple images using a specific trained model.

NOTE: The trained model is not included in this repository.

## How do I run the program? ##

Open the terminal and navigate to this directory. Type:

```
#!bash
python llnet.py
```

to launch the program with GUI. For command-line only interface, you type the following command in the terminal.

To train a new model, enter:

```
#!bash
python llnet.py train [TRAINING_DATA]
```

To enhance an image, enter:

```
#!bash
python llnet.py test [IMAGE_FILENAME] [MODEL_FILENAME]
```

For example, you may type:

```
#!bash
python llnet.py train datafolder/yourdataset.mat
python llnet.py test somefolder/darkpicture.png models/save_model.obj
```

where file names do not need to be in quotes.

Datasets need to be saved as .MAT file with the '-v7.3' tag in MATLAB. The saved variables are:

```
train_set_x     (N x wh)   Noisy, darkened training data
train_set_y     (N x wh)   Clean, bright training data
valid_set_x     (N x wh)   Noisy, darkened validation data
valid_set_y     (N x wh)   Clean, bright validation data
test_set_x      (N x wh)   Noisy, darkened test data
test_set_y      (N x wh)   Clean, bright test data
```

Where N is the number of examples and w, h are the width and height of the patches, respectively. Test data are mostly used to plot the test patches; in actual applications we are interested to enhance a single image. Use the test command instead.
