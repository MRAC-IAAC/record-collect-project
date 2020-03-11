# Space Optimization
## IAAC MRAC 19-20 // Hardware II // Group 03

Analysing human activities within a defined space, collecting and storing data of these activities by using detection and tracking algorithms and utilizing the collected data to implement it in processes of space optimization

![Final presentation (1)](https://user-images.githubusercontent.com/57528373/76356354-1a4e7080-6316-11ea-8ee5-429ab442cb1e.png)

### Before Detection and Tracking Algorithms
Example of tracking activities of people, observing, analysing and using that data to optimize the space so that it enhances the operation of those activities

[![](http://img.youtube.com/vi/jTageuhPfAM/0.jpg)](http://www.youtube.com/watch?v=jTageuhPfAM "Speedee Service System")


### Objectives
Use technology to our advantage to collect and store data of activities that are performed within a defined space.
![Final presentation 3](https://user-images.githubusercontent.com/57528373/76356363-1de1f780-6316-11ea-8268-58a6bcfced63.png)

### Experimentation Area
Testing space : a working environment that facilitates multiple activities throughout the day.
![Final presentation 4](https://user-images.githubusercontent.com/57528373/76356366-1fabbb00-6316-11ea-863a-6f80564f9d16.png)

### Current Methods
Showcasing some current methods of how spatial analysis is currently being evaluated
![Final presentation 5](https://user-images.githubusercontent.com/57528373/76356376-220e1500-6316-11ea-9bd4-c3de69fea49c.png)

### Initial Approach: Optical Flow
To extract data for out analysis we initially used "Optical Flow". Optical flow or optic flow is the pattern of apparent motion of objects, surfaces, and edges in a visual scene caused by the relative motion between an observer and a scene.
![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/57528373/76371636-1ed95000-633b-11ea-97b8-2642da96df52.gif)

### What is "Optical Flow"?
Optical Flow finds points of interest in a frame and tracks those points. 
![Final presentation 8](https://user-images.githubusercontent.com/57528373/76369394-b0dd5a80-6333-11ea-8c31-3a1b62f08791.png)


### Initial Experiment - Outcome
However, there is no control on the location of those points. Optical flow does not isolate object that are moving (people, animals, furniture etc.) In addition, reflections and shadows of a moving object are also becoming part of the trajectory. With Optical flow, while the trajectory of a moving object is being tracked, the end result becomes uncontrollable and noisy.
![ezgif com-video-to-gif (2)](https://user-images.githubusercontent.com/57528373/76372089-9f4c8080-633c-11ea-9f04-68b6aba66824.gif)

### Object Detection
This lead us into object detection. There are several object detectors. One of the first being R-CNN. However, RCNN is very slow because it extracts proposals from different regions of the input image, computes features by using a large CNN and classifies each region. 
![Final presentation 11](https://user-images.githubusercontent.com/57528373/76372198-eb97c080-633c-11ea-84a6-45cff397c625.png)

### YOLO
We chose to use YOLO, which is faster since we are using videos and we can get a speed of 45 Frames per Second. In addition, YOLO achieves object detection, classification and localization trained on a specific dataset.
![Final presentation 12](https://user-images.githubusercontent.com/57528373/76356533-626d9300-6316-11ea-978c-75e42798dadd.png)

### COCO Dataset
COCO dataset is trained on 200,000 images of 80 different categories (person, suitcase, umbrella, horse etc…). It Contains images, bounding boxes and 80 labels. COCO can be used for both object detection, and segmentation, we are using it for detecting people.
![Final presentation 13](https://user-images.githubusercontent.com/57528373/76356526-5f72a280-6316-11ea-9e00-ea0d03937da2.png)

### OpenCV
![Final presentation 14](https://user-images.githubusercontent.com/57528373/76356553-6a2d3780-6316-11ea-8b81-40254eb9e98e.png)

### How YOLO works
YOLO performs object detection by creating a rectangular grid throughout the entire image. Then creates bounding boxes based on (x,y) coordinates. Class probability gets mappedby  using random color assignment. To filter out weak detections, a 50% confidence is being used (this can change) which helps eliminate unnecessary boxes. (Right) this is what an output image looks like after being put through the neural network
![Final presentation 15](https://user-images.githubusercontent.com/57528373/76356555-6bf6fb00-6316-11ea-951e-05d4a5d83503.png)

### Tools
![Final presentation 16](https://user-images.githubusercontent.com/57528373/76370296-b1c3bb80-6336-11ea-85c0-10334c48a7d4.png)

### Methodology
![Final presentation 17](https://user-images.githubusercontent.com/57528373/76370297-b25c5200-6336-11ea-9e14-af760adcf806.png)

### Process
![Final presentation 18](https://user-images.githubusercontent.com/57528373/76370299-b25c5200-6336-11ea-9109-a1a102ad1195.png)
![Final presentation 19](https://user-images.githubusercontent.com/57528373/76356564-70bbaf00-6316-11ea-9711-e3ea7508a889.png)
![Final presentation 20](https://user-images.githubusercontent.com/57528373/76356565-72857280-6316-11ea-8782-9c9ec77d53e8.png)
![Final presentation 21](https://user-images.githubusercontent.com/57528373/76356577-76b19000-6316-11ea-8572-1c2303fe50c5.png)

### Workflow
![Final presentation 22](https://user-images.githubusercontent.com/57528373/76356579-787b5380-6316-11ea-89ca-0e629f5c1978.png)
![Final presentation 23](https://user-images.githubusercontent.com/57528373/76356585-7c0eda80-6316-11ea-93f0-fb8588613cf4.png)

### Test 02: Generating Heatmap
![Final presentation 27](https://user-images.githubusercontent.com/57528373/76356600-80d38e80-6316-11ea-9e67-a61caa7c4e95.png)
![Final presentation 28](https://user-images.githubusercontent.com/57528373/76356605-8335e880-6316-11ea-9364-eb9d4b368e54.png)

