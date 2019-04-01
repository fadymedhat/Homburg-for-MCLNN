
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://github.com/fadymedhat/Homburg-for-MCLNN/blob/master/LICENSE)

# HOMBURG dataset for MCLNN

The [Homburg](http://www-ai.cs.uni-dortmund.de/audio.html) music genre dataset.

| Clip Duration  | Format | Count | Categories|
|:---:|:---:|:---:|:---:|
| 10 secs | .mp3 | 1886 | 9 |

Dataset Summary:
 * clips are 10 seconds in length with 44100 Hz sampling rates.
 * No predefined split is defined for the dataset cross-validation.

 
 This folder contains:
  * Scripts required to prepare the Homburg dataset for the MCLNN processing.
  * Pretrained weights and indices for the 10-fold cross-validation in addition to the standardization parameters 
  to replicate the results in:
  
  _Fady Medhat, David Chesmore and John Robinson, "Music Genre Classification Using Masked Conditional Neural Networks.", International Conference on Neural Information Processing, ICONIP 2017._
 
 
 ## Prepossessing
 
The following are the steps involved in preparing the Homburg dataset:
1) Convert .mp3 to .wav 
2) Downsample the clips to 22050 Hz.


#### Preparation scripts prerequisites

The [preparation scripts](https://github.com/fadymedhat/Homburg-for-MCLNN/tree/master/Homburg_preparation_scripts) require the following packages to be installed beforehand:
   * [ffmpeg](https://www.ffmpeg.org/) version N-81489-ga37e6dd
   * numpy 1.11.2+mkl
   * librosa 0.4.0
   * h5py 2.6.0
 
#### Steps
1. Download the dataset and execute the scripts in the [preparation scripts](https://github.com/fadymedhat/Homburg-for-MCLNN/tree/master/Homburg_preparation_scripts) following the order of their labels.
2. Make sure the files are ordered following the [Homburg_storage_ordering](https://github.com/fadymedhat/Homburg-for-MCLNN/blob/master/homburg_storage_ordering.txt) file.
3. Configure the spectrogram transformation within the [Dataset Transformer](https://github.com/fadymedhat/MCLNN/tree/master/dataset_transformer) and generate the MCLNN-Ready hdf5 for the dataset.
4. Generate the indices for the folds using the [Index Generator](https://github.com/fadymedhat/MCLNN/tree/master/index_generator) script.
