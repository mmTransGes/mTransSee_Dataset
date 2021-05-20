# mTransSee_Dataset

This dataset contains the gesture samples used in mTransSee. This work utilizes a transfer learning-based method to reduce the dependence of the tedious adaptation process of previous works which are sensitive to user habits and position changes of mmWave gesture sensing. Besides, compared to the state-of-the-art work, this dataset further extends the detection range of the mmWave sensor, i.e., from 1.2m to 4.8m.

## Sample Gathering

The dataset is used to explore the dependence of the following practical environment issues over previous works:

**(a)** Different user habits: we recruit 32 different volunteers to perform each gesture 16-20 times and select the first 16 of them for further evaluations.

**(b)** Different positions: we place 13 equally spaced anchor positions between human-sensor distance (hs-Dis) in \[1.2m, 4.8m\], i.e., separated by 0.3m and ask all of the aforementioned 32 volunteers to repeat on each anchor. More than that, positions in practical home scenarios can be adjacent to some uneven reflection subjects sometimes. Therefore, we further ask 4 of the 32 volunteers to repeat the same gesture samples on each same anchor but under different scenarios, i.e., volunteers perform gestures while adjacent to 5 kinds of reflectors: the user is tightly next to (a) several chairs, (b) a movable metal table, (c) a square metal oven with a side length of 60cm on the gesture side equal to the height of user’s shoulder, (d) a 30-inch TV set close to the user’s back, and (e) gesturing arm with the same height as the shoulder.

<img src="https://github.com/mmTransGes/mTransSee_Dataset/blob/master/reflectors.png" width="300"  alt="reflectors"/><br/>

We define five arm-gestures to explore the impact of the above environment dependence and evaluate mTransSee. Here are the five gestures:

<img src="https://github.com/mmTransGes/mTransSee_Dataset/blob/master/gesturePic.png" width="400"  alt="gesturePic"/><br/>

We collect data from 32 persons with performing each gesture 16-20 times, in order to give mTransSee the ability to serve the gestures with different personal habits. We also set 13 discrete positions as anchor points between human-sensor distance, in order to give mTransSee the ability to serve the gestures from random positions, and collect data of repeating the same gesture samples on each same anchor but under 5 different environments, so as to make it available in practical environments.
To ensure the variety of users' habits, the volunteers learn the gestures by watching how we perform.

## Directory Structure

We divide the samples into two folders: "experimental_scenario_without_reflectors" and "five_scenarios_with_reflectors".
In each folder, the samples are further separated by different volunteers each of whom has a unique serial number (from 1 to 19 and from 80 to 92).
The samples of the same \[volunteer, human-sensor distance, gesture\] are gathered into one '.csv' file.
In each '.csv' file, we set the lost frames as the delimiter between samples. Specifically, we asked the volunteers to hold still for about 1 second after each action, in order to generate empty frames to be used as delimiters between each action.
Each sample's data structure is 7 * n, where n is various with frames and 7are ‘frame id’, ‘detected points in each frame’, ‘x coordinate of each point’, ‘y coordinate of each point’, ‘z coordinate of each point’, ‘velocity of each point’ and ‘reflection intensity of each point’.

We provide a gesture instruction (a pdf file) in the home directory which describes how to perform each arm gesture in detail. Note that however, the volunteers learn the gestures only by watching how we perform them.

## Sensor Configuration

In this mmWave gesture dataset, we utilize the TI-IWR1443 single-chip 77-GHz to 81-GHz mmWave sensor evaluation module. The parameters are as follows:

| Radar parameters | vaule |
| ----- | ----- |
| Rx channels | 4 |
| Tx channels | 3 |
| chirp cycle time | 158 μs |
| ADC sampling rate | 7.5 kHz |
| Rx gain | 42 dB |
| frame periodicity | 100 ms |
| dynamic point detection | CFAR-CA |
| point energy threshold | 1130 dB |
