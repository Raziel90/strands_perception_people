## Pedestrian Tracking
This package uses the data generated by ground_hog, visual_odometry und upper_body_detector to track pedestrians. It is also possible to omit the ground_hog detections.

### Run
Parameters:
* `queue_size` _default = 20_: The synchronisation queue size
* `config_file` _default = ""_: The global config file. Can be found in strands_upper_bodydetector/config
* `camera_namespace` _default = /head_xtion_: The camera namespace.
* `ground_plane` _default = /ground_plane_: The ground plane published by the upper_body_detector
* `ground_hog` _default = /groundHOG/detections_: The ground_hog detections
* `upper_body_detections` _default = /upper_body_detector/detections_: The upper_body_detector_detections
* `visual_odometry` _default = /visual_odometry/motion_matrix_: The visual_odometry data
* `pedestrain_array` _default = /pedestrian_tracking/pedestrian_array_: The resulting tracking data.
* `pedestrian_markers" default="/pedestrian_tracking/marker_array_: A visualisation array for rviz
* `pedestrian_poses" default = /pedestrian_tracking/pose_array_: A PoseArray of the detected pedestrians

rosrun:
```
rosrun strands_pedestrian_tracking pedestrian_tracker [_parameter_name:=value]
```

roslaunch:
```
roslaunch strands_pedestrian_tracking pedestrian_tracking.launch [parameter_name:=value]
```

To run the tracker without the groundHOG feture extraction running use:
```
rosrun strands_pedestrian_tracking pedestrian_tracker _ground_hog:=""
```
or

```
roslaunch strands_pedestrian_tracking pedestrian_tracking_no_HOG.launch [parameter_name:=value]
```