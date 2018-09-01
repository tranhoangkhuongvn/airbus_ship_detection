# Downloading the data

First, you should accept the competition conditions. Then, after installing  the Kaggle CLI, create a `data` folder
under `asd` and run the following command inside it:

`kaggle competitions download -c airbus-ship-detection`


# Baseline


Notice that, since the "no ship" class is predominate, submitting a file with empty values for the `EncodedPixel`
columns leads to a `0.847` score on the public leaderboard. This will probably be different in the private leaderboard.
It is thus necessary to account for this imbalance in order to get good performances.


# Resources

* https://www.kaggle.com/c/data-science-bowl-2018/discussion/54741 => a great post about advanced instance segmentation tricks. This is the winning solution for the data bowl 2018 challenge. 

* https://github.com/ZFTurbo/ZF_UNET_224_Pretrained_Model => Unet-like model with pretrained weights. To try later. 
