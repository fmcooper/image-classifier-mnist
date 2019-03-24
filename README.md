# image-classifier-mnist Readme
This program uses deep learning to classify MNIST or fashion-MNIST image data. 

<a href="https://colab.research.google.com/github/fmcooper/image-classifier-mnist/blob/master/ImageClassifier.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

******************************

1) Program use
2) Google Drive access
3) Results

******************************

## 1) Program use

You will need to have a Google account to access colab. If you have never used colab before take a look <a href="https://colab.research.google.com/notebooks/welcome.ipynb">here</a>. After this, simply click on the following button to open this program in a new colab instance: 
<a href="https://colab.research.google.com/github/fmcooper/image-classifier-mnist/blob/master/ImageClassifier.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

The following variables are available to change: ``NUM_EPOCHS``, ``BATCH_SIZE``, 
* ``SHOW_IMAGES`` may be set as ``True`` or ``False``
* ``DATASET_NAME`` may be set as ``'mnist'`` or ``'fashion_mnist'``
* ``NN_TYPE`` (neural network type) may be set as ``'standard'`` or ``'cnn'``
* ``NUM_EPOCHS`` should be a positive integer
* ``BATCH_SIZE`` should be a positive integer
* Result file locations may also be set. Please see Results section.


## 2) Google Drive access

In order to save the model both during and after training, this program will ask you for google drive access. If you don't want to give access, please comment out the following lines:

```
from google.colab import drive
drive.mount('/content/gdrive')
```

and change this line


```
CHECKPOINT_DIR = F'/content/gdrive/My Drive/Colab/imageClassifier/checkpoints/' + "epochs" + str(NUM_EPOCHS) + "_batchsize" + str(BATCH_SIZE) + "/"     # directory checkpoint weights of model are saved
```

to this:

```
CHECKPOINT_DIR = F'/content/checkpoints/' + "epochs" + str(NUM_EPOCHS) + "_batchsize" + str(BATCH_SIZE) + "/"     # directory checkpoint weights of model are saved
```

Now your results files will be saved in the colab virtual machine.

## 3) Results

Checkpoints are saved after each epoch and the entire model is saved after all training. These are reloaded into the program during the testing phase to show how they work. Checkpoints and the entire model are saved to the following directory in your Google Drive: ``Colab/imageClassifier/checkpoints/epochs<NUM_EPOCHS>_batchSize<BATCH_SIZE>/``. In order to change this, please edit the ``CHECKPOINT_DIR`` constant.
