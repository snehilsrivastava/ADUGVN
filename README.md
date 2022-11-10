### Real-Time Anomaly Detection for Unmanned Ground Vehicles 

**[\[paper\]](https://ieeexplore.ieee.org/document/9720937)**

## Abstract
Despite the rapid advancement of navigation algorithms, mobile robots often produce anomalous behaviors that can lead to navigation failures. We propose a proactive anomaly detection network (PAAD) for robot navigation in unstructured and uncertain environments. PAAD predicts the probability of future failure based on the planned motions from the predictive controller and the current observation from the perception module. Multi-sensor signals are fused effectively to provide robust anomaly detection in the presence of sensor occlusion as seen in field environments. Our experiments on field robot data demonstrate superior failure identification performance than previous methods, and that our model can capture anomalous behaviors in real-time while maintaining a low false detection rate in cluttered fields.

## Description of the code
More detailed comments can be found in the code. Here are some general descriptions:
* `nets`: Contains network architectures for PAAD.

* `train.py` and `test.py`: Train and test PAAD on the dataset, respectively.

* `custom_dataset.py`: Loads the dataset from CSV files and image folders.

* `dataset_vis.py`: Visualizes a datapoint in the dataset. The annotated planned trajectory is projected onto the front-view image, and the 2D lidar scan around the robot is plotted.

* `utils.py`: Contains the code for loss functions and metrics for quantitative results.

* `rosnode`: Contains a rosnode which performs proactive anomaly detection in real-time using PAAD.

The training set consists of 29292 datapoints and contains 2258 anomalous behaviors, while the test set consists of 6869 datapoints and contains 689 anomalous behaviors.

The 6 rosbags used for the real-time test were collected on additional days and contain all the necessary perception signals for PAAD. The detailed related rostopics can be found in the sample code provided in `rosnode`.
