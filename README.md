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
![Final presentation 4](https://user-images.githubusercontent.com/57528373/76411340-eadd4980-6391-11ea-8fb1-e2dd0f550e9e.png)

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
![Final presentation 14qa](https://user-images.githubusercontent.com/57528373/76411532-4e677700-6392-11ea-99e4-52ccad839604.png)

### Tools
![tools](https://user-images.githubusercontent.com/57528373/76411694-9c7c7a80-6392-11ea-808e-70c0282fdcd7.png)

### Methodology
![Final presentation 17](https://user-images.githubusercontent.com/57528373/76370297-b25c5200-6336-11ea-9e14-af760adcf806.png)

### Workflow
![workflow](https://user-images.githubusercontent.com/57528373/76411901-03019880-6393-11ea-94d5-c0f7b7cc5dd3.png)

### How YOLO Works
YOLO performs object detection by creating a rectangular grid throughout the entire image. Then creates bounding boxes based on (x,y) coordinates. Class probability gets mappedby  using random color assignment. To filter out weak detections, a 50% confidence is being used (this can change) which helps eliminate unnecessary boxes. (Right) this is what an output image looks like after being put through the neural network
![how yolo works](https://user-images.githubusercontent.com/57528373/76411975-21679400-6393-11ea-88cf-6b6ba399cea4.png)

### Filtering Out Unnecessary Detections
![filtering out](https://user-images.githubusercontent.com/57528373/76412046-3e03cc00-6393-11ea-804b-0f82dc1dca8e.png)

### Tools
![tools20](https://user-images.githubusercontent.com/57528373/76412144-64296c00-6393-11ea-80ba-c96332baf315.png)

### Mapping of Data -- Methodology
The video output is necessary to visualize the data. However, to map the data from a video, we need a process that can map those points on a 2D plan. We use Homography inside Grasshopper to read and process the files that contain the list of (x,y) coordinates.
![mapping of data](https://user-images.githubusercontent.com/57528373/76412293-a9e63480-6393-11ea-834f-3a6080d66873.png)

### Workflow
![workflow22](https://user-images.githubusercontent.com/57528373/76412410-dac66980-6393-11ea-865e-15e7f69a7852.png)

### Process(EDIT)
![process25](https://user-images.githubusercontent.com/57528373/76412679-4a3c5900-6394-11ea-9e17-3b03b331e503.png)

### Tools
![tools27](https://user-images.githubusercontent.com/57528373/76412748-748e1680-6394-11ea-9299-1952a7687147.png)

### Test 01:
![fafa](https://user-images.githubusercontent.com/57528373/76413318-7dcbb300-6395-11ea-98b8-3dd5f40e1794.gif)
![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/57528373/76414504-bf5d5d80-6397-11ea-95a3-aaef98dacfb8.gif)

### Test 02: 
Generating occupany heatmap
![test02](https://user-images.githubusercontent.com/57528373/76414628-ff244500-6397-11ea-93ca-0329d02e0b23.png)
![test02a](https://user-images.githubusercontent.com/57528373/76414632-00557200-6398-11ea-9ef0-829899f50455.png)



