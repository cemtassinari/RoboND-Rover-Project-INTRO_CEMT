## Project: Search and Sample Return by CEMT
### Some basic comments about this first project
---


**The goals / steps of this project are the following:**  

**Autonomous Navigation / Mapping**

* Download the simulator and take data in "Training Mode" - Checked
* Test out the functions in the Jupyter Notebook provided - Checked 
* Add functions to detect obstacles and samples of interest (golden rocks) - Checked
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` you create in this step should demonstrate that your mapping pipeline works. - Checked
* Use `moviepy` to process the images in your saved dataset with the `process_image()` function.  Include the video you produce as part of your submission. - Checked

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook).  - Checked
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands.  - Checked
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  - Checked


[//]: # (Image References)

[image1]: ./cemt_data_test/IMG/robocam_2017_06_05_00_54_22_838.jpg
[image2]: ./cemt_output/threshed_grid.jpg
[image3]: ./cemt_output/threshed_rock.jpg
[image4]: ./calibration_images/Image_Setting.jpg


## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  


* The trainnning and calibration tests were done using te help of the Rover_Project_Test_Notebook_CEMT notebooks
* In this tests the array of threshed limits were sintonized, first with de data provided, then using data from "../cemt_output"
* Once the best chooices were maden, complete  perception_step was not that chalengying. The main change was to filter the pixels with the best accuracy. ( the ones closers to the rover )
* In the decision step was incremented the option to go in the direction of a rock. So the future idea, would be to try to get them all. 

### Notebook Analysis
#### 1. With the simulator setted and functions tested, it was possible to record data in the trainnning mode. Here is an example of some frame of the data recorded:

![alt text][image1] 

#### 2. After I was able to work with my own data, I start to fulfill the functions with the best thresh limits I could find.

 ![alt text][image2] ![alt text][image3]

### Autonomous Navigation and Mapping

#### 3. Getting better results and running `perception_step()` and `decision_step()` and `drive_rover.py()` functions in the autonomous mapping.

###### I could achieve the goal of the project without changing the functions far beyond of the suggestions made in the notebook.
###### In my first attempt, my fidelity was really low, even with my improvements in the notebook. 
###### So, I looked for different ways of improving the rover. Setting differents conditions. 
###### But, it have only gotten better, after I added some filter to penalyzed inaccurate pixels. Also, I added one condition to not consider the perception if the calibration is inaccurate, due to pitch movements.
###### I've made some changes in the decision tree for trying to start to get some rocks. Though, its just a preliminary step. I want to continue to work in that issue

##### 2. Launching in autonomous mode your rover can navigate and map autonomously.
###### Here I show some results/analysis of the rover in the autonomous mode:
###### More than 60 % of area mapped within more than 70% of fidelity. (see"../video_auto") ;
###### Rock Obtained (see"../autodrive2")  -> But with a very bad aproach -> Tha demonstraded a need of evolving the decision;
###### Moments where the rover get stucked (see.."/autodrive2") -> Again an urge of evolving the decision tree;
###### Strong inverse correlation between area mapped and time of mapping.

**Note: I recorded 2 runs that are saved in the folders: "../video_auto" and "../autodrive2" . The visual settings are shown below  **
 ![alt text][image3]






