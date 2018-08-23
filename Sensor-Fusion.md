---
layout: page-2
title: Sensor Fusion
---

**Definition:**

Sensor fusion is the art of combining data from several sensors (Lidar, Radar, Cameras) to create the most accurate understanding of the environment around a car where an individual sensor will be less effective.

**Overview of Sensor Fusion:**

Each individual sensor has its limitations. However, by combining the raw data of the various sensors, the individual sensors are able to complement each other to better understand the environment around the car. Sensor fusion will enable enhanced ADAS functions such as lane keeping or lane switching. Today, much of the ADAS installed in vehicles operate using individual sensors because these vehicles lack the localized compute ability and software for sensor fusion.

![sensor_fusion_1](/assets/pictures/sensor_fusion_1.jpg){:class="img-responsive"}*Diagram of Kalman Filter*

**A Method for Sensor Fusion:**

The Kalman filter is the most common and very powerful sensor fusion algorithm for position and tracking approximation. The idea of the Kalman filter is that it takes in a number of measurements from each sensor (Radar, Lidar, Camera) acknowledging that each measurement will be inaccurate to a degree.  Note that there are other techniques, but they are not covered in this guide.

The filter is a recursive two-step process, meaning it loops over and over again.

**1. Predict:** Makes estimations of the current variables and uncertainties

**2. Update:** Makes an update to the predicted state based on the prior prediction and current measurement

![sensor_fusion_2](/assets/pictures/sensor_fusion_2.png){:class="img-responsive"}*Kalman Filter summarized in two simple steps*

**Example:** An autonomous vehicle will take in data from each of its primary sensors (Radar, Lidar, Camera). For the sake of explaining a Kalman filter, let’s assume the car is only using one sensor, a Lidar. As the vehicle moves, it receives data (a prediction of what is around the vehicle). The Lidar will take in millions of measurements every second, which represent the millions of predictions. In between each of the predictions, the update step takes place where the vehicle uses the measurement to update its prior belief. As you can see, the LiDAR sensor, in good conditions, is able to get an accurate understanding because it is constantly measuring and updating its location, thousands to millions of times a second.

In the scenario of multiple sensors, think about having Radar, Lidar and a Camera. Each one has its own predict-update cycle. Its belief about its position and velocity are updated asynchronously each time a measurement is received regardless of the source of the sensor, and sensor fusion is at the heart of this constant iteration to locate the vehicle and the objects around it.

In practice, the measurements gathered from the sensors generate a lot of noise (data that needs to be cleaned), so leveraging the capabilities of each of the sensor’s strengths through sensor fusion makes the autonomous driving system much more robust.

**Two Sensor Camps**

A necessary and relevant point to discuss here is what sensors are necessary for sensor fusion. There are two camps of extremely intelligent individuals who are split between the two. The way, there is really a divide between human centered autonomy or fully autonomous.

Human centered autonomy means that the autonomous vehicle will have control 90%+ of time, but in an edge case (a scenario that the autonomous system can’t handle), the human will be expected to take over. For the most part, this camp believes that Lidar is not necessary. Notable companies following the human centered autonomy mold are Tesla, AutoX.

On the other hand, there is the fully autonomous camp that believes the autonomous vehicle should control the vehicle 100% of the time because they believe that it is impossible to assume that a human can safely take control of the vehicle during a hazardous situation. Again, for the most part, the fully autonomous camp is using a wide variety of Lidars in order to receive optimal results from sensor fusion. Notable companies following the fully autonomous camp are Waymo, Uber and Cruise.

The merits of both camps are valid, but I believe almost all companies will eventually use Lidar because the value it provides at lower costs make the sensor a value-added component within an autonomous driving system that can be reproduced with scale and efficiency. In addition, I wanted to note that the reason people believe in human centered autonomy is because not only do many engineers believe that full autonomy will not be possible for several decades, but that the last bit of autonomy is perceived not to be worth the incremental cost. Some see human centered autonomy as the intermediary step to make fully autonomous vehicles a reality, while others see a leap, skipping past human centered autonomy.

**Sensor Fusion Considerations**

There are a number of factors to consider when thinking about what sensors make sense on an autonomous vehicle. 

The most important ones in my opinion are:

**1. Reliability:** most important because lives are at risk if sensors fail

**2. Cost:** need to be low for AVs to gain mass adoption

**3. Size:** sensors need to fit on varying models of cars of all sizes

**4. Redundancy:** goal is to minimize redundancy without compromising safety, which will be important to keep sensor hardware costs down

**Performance Variance in Different Conditions**

These diagrams below represent graphs I found online to help with understanding the capabilities of each sensor. The higher the number for a certain category, the better the sensor is in that category.

In summary, each sensor has its own strengths and weaknesses that we must understand. The final diagram represents sensor fusion without the use of a Lidar to illustrate the human centered autonomy camp. As you can see, it fares extremely well. However, I want to point out that when dealing with human lives, these autonomous vehicles must be designed as a safety-critical system and even a small improvement in performance can make all the difference between an AV seeing a pedestrian or not seeing him/her.