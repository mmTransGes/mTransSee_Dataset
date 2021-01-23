# mTransSee_Dataset

This dataset contains the gesture samples used in mTransSee. 
This work utilizes transfer learning based method to reduce the dependence of tedious adaptation process of previous works which are sensitive to user habits and position changes of mmWave gesture sensing.
The dataset is collected by millimeter-wave (mmWave) FMCW radar as a benchmark for 5 gestures within 1.2 meters to 4.8 meters.

## Sample Gathernig

The dataset is used to explore the dependence of the following practical environment issues over previous works:

**(a)** Different user habits: we recruit 32 different volunteers to perform each gesture 16-20 times and select the first 16 of them for further evaluations.

**(b)** Different positions: we place 13 equally spaced anchor positions between human-sensor distance (hs-Dis) in \[1.2m, 4.8m\], i.e., separated by 0.3m and ask all of the aforementioned 32 volunteers to repeat on each anchor. More than that, positions in practical home scenarios can be adjacent to some uneven reflection subjects sometimes. Therefore, we further ask 4 of the 32 volunteers to repeat the same gesture samples on each same anchor but under different scenarios, i.e., volunteers perform gestures while adjacent to 5 kinds of reflectors: the user is tightly next to (a) several chairs, (b) a movable metal table, (c) a square metal oven with a side length of 60cm on the gesture side equal to the height of user’s shoulder, (d) a 30-inch TV set close to the user’s back, and (e) gesturing arm with the same height as the shoulder.

In this dataset, we define 5 gestures for recognition to facilitate the natural human computer interactions in a real-world home scenario. Our gestures can be performed frequently and much easier than whole-body activities, especially for the senior. In addition to these predefined gestures, the dataset also archives random actions at random positions in daily life, which can be used as source domain to amplify target domain via the method of transfer learning in mTransSee. Specifically, the 5 gestures are as follows:
