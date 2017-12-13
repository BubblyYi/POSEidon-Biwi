# POSEidon: Face-from-Depth for Driver Pose Estimation
Implementation in **Keras** and **Theano** of my paper published in **CVPR 2017** (Borghi G., Venturelli M., Vezzani R., Cucchiara R.).

## How To

### Configuration
The model has been tested with the following configuration:
- Python 2.7
- OpenCV 2.4.11
- Keras 1.0.6
- Theano

### Dataset (Biwi)
In order to run the code, it is necessary download the dataset from [here](https://data.vision.ee.ethz.ch/cvl/gfanelli/head_pose/head_forest.html) and following these steps:
- Create a folder for each run of each subject, naming from the number 01 to 24
- In each sub folder, a file named *angles.txt* is required, where the first column is the frame number, then the roll, pitch and yaw angles.

It is necessary create the Motion Images (through the Farnerback algorithm) and the reconstructed grey images from the corresponding depth ones. In the ```Dataset``` directory you can find one test sequence with these types of data. We plan to release the complete dataset in the next future.

<p align="center">
 <img src="https://github.com/gdubrg/POSEidon-Biwi/blob/master/Dataset/face_dataset_large/11/frame_00003_face_depth.png" width="100" />
 <img src="https://github.com/gdubrg/POSEidon-Biwi/blob/master/Dataset/face_dataset_ae/11/frame_00003_face_gray.png" width="100" />
 <img src="https://github.com/gdubrg/POSEidon-Biwi/blob/master/Dataset/face_dataset_OF/11/frame_00004_face_OF.png" />
 </p>

### Train and Test
 The command to train the network is
```
python3 train.py
```
and to test is
```
python3 test.py
```
and finally ```plot_error``` to plot the error and some graph. 
For both, you must pass the following arguments:
- ```cpu``` or ```gpu0...gpun``` to run the script on cpu or on the *n*-th gpu
- ```1...n``` quantity of memory allocated in gpu device 

## Results
Input cropping is done using the ground truth head position.

| Pitch   | Roll               | Yaw              | Avg  |
| :---:        |     :---:         |            :---: | :---:     |
|1.6 +/- 1.7       | 1.8 +/- 1.8        | 1.7 +/- 1.5       |  1.7 +/- 1.7    |
 

## Note

### Keras version
If you do not use Keras 1.0.6, scripts will run but thay will not produce the same reults reported in the original paper.

### Path
In the code are present some hardcoded paths, at the beginning of ```train``` and ```test``` scripts.

