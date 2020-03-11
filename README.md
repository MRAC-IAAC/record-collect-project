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

### Data Extraction - Methodology
We Input a video into the YOLO network. YOLOv2 trained on COCO dataset performs the object detection and localization. We create and output video through which we are able to visualize the detections with the Class IDs and confidences for each single detection. In addition, we use the algorithm to store points (x,y) in empty lists that we created and export them in a .csv file that we can later use to get the positions of the tracked objects.
![data ext](https://user-images.githubusercontent.com/57528373/76416360-3b0cd980-639b-11ea-9b44-d1935a3c3b02.png)

### Data Visualization - Methodology

![data vis](https://user-images.githubusercontent.com/57528373/76416546-963ecc00-639b-11ea-93a9-3b9b451ea0ef.png)

### How YOLO Works
YOLO performs object detection by creating a rectangular grid throughout the entire image. Then creates bounding boxes based on (x,y) coordinates. Class probability gets mappedby  using random color assignment. To filter out weak detections, a 50% confidence is being used (this can change) which helps eliminate unnecessary boxes. (Right) this is what an output image looks like after being put through the neural network
![how yolo works](https://user-images.githubusercontent.com/57528373/76411975-21679400-6393-11ea-88cf-6b6ba399cea4.png)

### Filtering Out Class IDs
![classiad](https://user-images.githubusercontent.com/57528373/76422008-d5bde600-63a4-11ea-889f-e9127c7191bd.png)

### Mapping of Data -- Methodology
The video output is necessary to visualize the data. However, to map the data from a video, we need a process that can map those points on a 2D plan. We use Homography inside Grasshopper to read and process the files that contain the list of (x,y) coordinates.
![map20](https://user-images.githubusercontent.com/57528373/76427708-effbc200-63ac-11ea-9306-752378857b3b.png)

### Failures: 
![1](https://user-images.githubusercontent.com/57528373/76421070-65629500-63a3-11ea-8c91-dfd3e00b8483.gif)
![2](https://user-images.githubusercontent.com/57528373/76420932-33e9c980-63a3-11ea-8084-1343f818c372.gif)
![3](https://user-images.githubusercontent.com/57528373/76420881-1e749f80-63a3-11ea-9df3-a27060586f12.gif)
![4](https://user-images.githubusercontent.com/57528373/76420882-1fa5cc80-63a3-11ea-90b0-874d4095d62c.gif)
![5](https://user-images.githubusercontent.com/57528373/76420884-203e6300-63a3-11ea-9207-306a1bb60408.gif)
![6](https://user-images.githubusercontent.com/57528373/76420885-20d6f980-63a3-11ea-9716-a7b2925b6a6e.gif)
![7](https://user-images.githubusercontent.com/57528373/76420887-216f9000-63a3-11ea-80dc-6701345e5084.gif)
![8](https://user-images.githubusercontent.com/57528373/76420890-22082680-63a3-11ea-8543-e5444addfa07.gif)

### Workflow
What we need for the homography process: 3 types of points
![workflow22](https://user-images.githubusercontent.com/57528373/76424067-094e3f80-63a8-11ea-8f02-d56dd8a2ab93.png)

Homography process: Relating two images, or in our case sets of points, by defining a plane they have in common which we do by using markers. Then the points from the video are mapped to the floor plan and we can start generating the heatmap.
![workflow23](https://user-images.githubusercontent.com/57528373/76424220-3dc1fb80-63a8-11ea-992e-972451ece0d7.png)

### Test 01:
This is one of the first videos we used to test this process:
![fafa](https://user-images.githubusercontent.com/57528373/76413318-7dcbb300-6395-11ea-98b8-3dd5f40e1794.gif)

Here you can see the difference between the points from the video and when we map them to the floor plan:
![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/57528373/76414504-bf5d5d80-6397-11ea-95a3-aaef98dacfb8.gif)

### Test 02: 
After mapping the points we started generating a heatmap.
1. divide space into grid
2. count point in each square
3. assign color to square by the number of points that are in it
![testo2a](https://user-images.githubusercontent.com/57528373/76424739-ecfed280-63a8-11ea-8737-44c3f754eeb8.png)

### Test 03: 
The result displays which areas of the space are being used more frequently. We tend to use this information in the design process and to be able to generate floor plans based on activity after analysing the results based on a bigger dataset.
![testo3](https://user-images.githubusercontent.com/57528373/76427867-318c6d00-63ad-11ea-9af4-1d152bcd4d44.png)

### Summary: 
![summary](https://user-images.githubusercontent.com/57528373/76428055-757f7200-63ad-11ea-84cf-f707521df9c5.png)

