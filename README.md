# Downloading the data

First, you should accept the competition conditions. Then, after installing  the Kaggle CLI, create a `data` folder
under `asd` and run the following command inside it:

`kaggle competitions download -c airbus-ship-detection -o -w`


# Unzipping the data

`unzip airbus_ship_detection/asd/data/test_v2.zip -d airbus_ship_detection/asd/data/train_v2`
`unzip airbus_ship_detection/asd/data/test_v2.zip -d airbus_ship_detection/asd/data/test_v2`


# Baseline

Notice that, since the "no ship" class is predominate, submitting a file with empty values for the `EncodedPixel`
columns leads to a `0.847` score on the public leaderboard. This will probably be different in the private leaderboard.
It is thus necessary to account for this imbalance in order to get good performances.

# Submission

Generate the submission file using the `run.py` script. Then, use the Kaggle API tool as follows:

`kaggle competitions submit -c airbus-ship-detection -f /path/to/submission/file -m "Model description message"`

# Sanity check

`ls train_v2 -1 | wc -l`

should return: 192556

and

`ls test_v2 -1 | wc -l`

should return: 15606


# Data leakage

It appears that the test images are transformed images for the train ones (translated and cropped images).
Thus, the test masks have been release. New test data should be available in the upcoming days (or weeks).
For more details, check this [discussion](https://www.kaggle.com/c/airbus-ship-detection/discussion/64388).

The new data is available and ends with `_v2`.

# Resources

* https://www.kaggle.com/c/data-science-bowl-2018/discussion/54741 => a great discussion post about advanced
instance segmentation tricks. This is the winning solution for the data bowl 2018 challenge.
* https://www.kaggle.com/c/tgs-salt-identification-challenge/discussion/69291 => another great discussion post about
the winning model for TGS competition.
* https://github.com/qubvel/segmentation_models => a great segmentation framework (pretrained weights and
  common architectures).
* https://github.com/ZFTurbo/ZF_UNET_224_Pretrained_Model => U-net architecture with pre-trained weights. To try later.
* https://arxiv.org/pdf/1801.05746.pdf => TernausNet model: U-net architecture with pre-trained VGG11 encoder.
The github repo is here: https://github.com/ternaus/TernausNet.
