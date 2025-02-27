# UWB Localization
This repository contains the UWB data sets for localizization and NLoS classification. It contains also implementations of localization algorithms, localization error mitigation algorithms and NLoS classification and error regression building code. Ranging error regression and classification algorithms are implemented using [TensorFlow](https://www.tensorflow.org/) framework.

## Installation
The code needs the following python modules:
	- numpy
	- scikit-learn
	- tensorflow

### Installation on Ubuntu with Virtualenv
Installing Python software with Virtualenv can be useful to separate main system Python installation from separate installation with distinctive set of features and libraries installed. This prevents breaking the existing installation of Python and libraries.

###### 1. Install pip and Virtualenv:	
	$ sudo apt-get install python-pip python-dev python-virtualenv    # Python 2.7
	$ sudo apt-get install python3-pip python3-dev python-virtualenv  # Python 3.n

###### 2. Create a new virtual environment (in this case it's named 'tf' and is placed in ~/tf):
	$ virtualenv --system-site-packages ~/tf             # Python 2.7
	$ virtualenv --system-site-packages -p python3 ~/tf  # Python 3.n

###### 3. Activate the new virtual environment 'tf':
	$ source ~/tf/bin/activate

###### 4. Install the latest pip:
	(tf)$ easy_install -U pip

###### 5. Install tensorflow in the activated 'tf' virtual environment:
	(tf)$ pip install --upgrade tensorflow       # Python 2.7
	(tf)$ pip3 install --upgrade tensorflow      # Python 3
	(tf)$ pip install --upgrade tensorflow-gpu   # Python 2.7 with gpu support
	(tf)$ pip3 install --upgrade tensorflow-gpu  # Python 3 with gpu support
	
If the installation process fails, for more details check the official [Tensorflow installation instructions](https://www.tensorflow.org/install/)

###### 6. Install Pandas Python package:
	(tf)$ pip install pandas   # Python 2.7
	(tf)$ pip3 install pandas  # Python 3
	
###### 7. Install scikit-learn Python package:
	(tf)$ pip install sklearn   # Python 2.7
	(tf)$ pip3 install sklearn  # Python 3
	
###### 8. Install scipy Python package:
	(tf)$ pip install scipy   # Python 2.7
	(tf)$ pip3 install scipy  # Python 3

## Using the software

### Building the models
For NLoS classification and ranging error regression models need to be built respectively. 	

**Note:** all scripts can be run only in a Python environment, where the Tensorflow is installed. If you installed Tensorflow using Virtualenv (as is presented in this tutorial), the selected **tf** virtual environment should be activated before running the scripts.

##### Building the NLoS classification model:

	# Inside the folder NLOSClassificationModel run scrip build_classification_model.py
	(tf)$ python build_classification_model.py    # Python 2.7
	(tf)$ python3 build_classification_model.py   # Python 3

**Note**: The process of training the classification model takes around 15 minutes on an average computer.

##### Building the ranging error regression model
	
	# Inside the folder RangingErrorModel run script build_regression_model.py
	(tf)$ python build_regression_model.py    # Python 2.7
	(tf)$ python3 build_regression_model.py   # Python 3

**Note**: The process of training the classification model takes around 2.5 hours on an average computer.


### Running the localization scripts
To run localization evaluation scripts using classification and error regression techniques to mitigate the effects of ranging errors, check the contents of the folder **evaluation**.

## Citation
If you are using our data set in your research, citation of the following paper would be greatly appreciated.

Plain text:

	K. Bregar and M. Mohorčič, "Improving Indoor Localization Using Convolutional Neural Networks on Computationally Restricted Devices," in IEEE Access, vol. 6, pp. 17429-17441, 2018.
	doi: 10.1109/ACCESS.2018.2817800
	keywords: {Computational modeling;Convolutional neural networks;Distance measurement;Estimation;Heuristic algorithms;Performance evaluation;Prediction algorithms;Channel impulse response;convolutional neural network;deep learning;indoor localization;non-line-of-sight;ranging error mitigation;ultra-wide band},
	URL: http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8320781&isnumber=8274985
	

BibTeX: 

	@ARTICLE{8320781,
		author={K. Bregar and M. Mohorčič},
		journal={IEEE Access},
		title={Improving Indoor Localization Using Convolutional Neural Networks on Computationally Restricted Devices},
		year={2018},
		volume={6},
		number={},
		pages={17429-17441},
		keywords={Computational modeling;Convolutional neural networks;Distance measurement;Estimation;Heuristic algorithms;Performance evaluation;Prediction algorithms;Channel impulse response;convolutional neural network;deep learning;indoor localization;non-line-of-sight;ranging error mitigation;ultra-wide band},
		doi={10.1109/ACCESS.2018.2817800},
		ISSN={},
		month={},}
		
## Author and license
Author of code and data sets in this repository is Klemen Bregar, **klemen.bregar@ijs.si**.

See README.md files in individual sub-directories for details. 

Copyright (C) 2018 SensorLab, Jožef Stefan Institute http://sensorlab.ijs.si

## Acknowledgement
The research leading to these results has received funding from the European Horizon 2020 Programme project eWINE under grant agreement No. 688116.