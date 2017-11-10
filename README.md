# POSEidon: Face-from-Depth for Driver Pose Estimation
Implementation in **Keras** and **Theano** of my paper published in **CVPR 2017** (Borghi G., Venturelli M., Vezzani R., Cucchiara R.).

## How To

### Configuration
The model has been tested with the following configuration:
- Python 2.7
- OpenCV 2.4.11
- Keras 1.0.6
- Theano

### Dataset
In order to run the code, it is necessary download the dataset from [here](http://imagelab.ing.unimore.it/pandora/) and following these steps:
- Create a folder for each run of each subject, naming from the number 000 to 100
- In each sub folder, a file named angles.txt is required.

### Train and Test
 The command to train the entwork is
```
python3 train.py
```
and to test is
```
python3 test.py
```
For both, you must pass the following arguments:
- ```cpu``` or ```gpu0...gpun``` to run the script on cpu or on the *n*-th gpu
- ```1...n``` quantity of memory allocated in gpu device 

## Results
Input cropping is done using the ground truth head position.

| Pitch   | Roll               | Yaw              | Avg  |
| :---:        |     :---:         |            :---: | :---:     |
|1.6 +/- 1.7       | 1.8 +/- 1.8        | 1.7 +/- 1.5       |  1.7 +/- 1.7    |


### Path
In the code are present some hardcoded paths, at the beginning of ```train``` and ```test``` scripts.

