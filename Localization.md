---
layout: page-2
title: Localization
---

![localization_1](/assets/pictures/localization_1.jpg){:class="img-responsive"}*Autonomous vehicle localizing itself using pre-built 3D maps and its sensor data*

**Definition:**

Localization is the process of determining the exact position of an autonomous vehicle in relation to its surroundings.

**Why is localization important?**

As human beings, when we are trying to get from one spot to another, we need to develop a general understanding of (i) where we are, (ii) where we want to go and can figure out (iii) how to get there. When an autonomous vehicle attempts to get from one location to another, it needs to gather the same information. This information is crucial for an AV to drive autonomously.

**Can we localize using only a GPS for urban driving?**

No we cannot. GPS is the most common system for localization used today, but it can only be used to an accuracy of ~1-2 meters. In addition, GPS may suffer from several other technical restrictions including satellite blockage in dense environments, atmospheric conditions and satellite geometry. Unfortunately, the technical restrictions and standard error are too large to safely drive an autonomous vehicle in a dense urban environment. The rule of thumb is that the AV needs to achieve accuracy within a few centimeters to drive safely.

**Primary Framework for Localization**

**How do we localize?**

Localization today generally uses pre-built maps created using a mapping vehicle driving down the road with a sensor suite to build a HD map of the environment. These maps must be accurate down to the centimeter, which as we discussed earlier is necessary for safe autonomous driving. The 3-D HD model is loaded into the AV system, which provides the autonomous vehicle with a baseline understanding of the environment it will be navigating around. In the scenario that the AV does not have a map to work off, it must rely on a technique called Simultaneous Localization and Mapping (SLAM).

However, to my knowledge, all autonomous driving companies that are being tested today have mapped pre-defined regions that they are testing their cars. AVs today struggle with real-time sensing and perception, which is computationally complex and puts an enormous computational burden on the “brain” of the car. Therefore, companies today use pre-mapped environments within their AV systems, an important point to understand.

![localization_2](/assets/pictures/localization_2.png){:class="img-responsive"}*HD Live Map created by HERE Technologies, a company providing critical mapping and location data to individuals and companies*

**Mapping**

Mapping as defined in the context of autonomous driving generally refers to a 3-D HD representation of the environment. There is an enormous market today for companies collecting data to accumulate knowledge of the physical world that can be used to train autonomous vehicles. An important point to note is that maps must constantly be refreshed to capture any changes in the mapped environments.

**What types of maps?**

**1. Location-based Maps:** Notable due to its ease of implementation and serves an important purpose in determining if a certain region is open or blocked by an object, which is essential for an AV to understand the areas it can move into. Among the 3 types of maps, it consumes the most memory due to the immense amount of data required for defining whether a region is open or blocked.

**2. Feature-based Maps:** Extracts geometric features to create a visual model and understanding of the world. For example, a lane marker would be identified as a line and a tree would be identified as a point feature. The key is that feature-based maps will primarily store distinct physical landmarks to reduce memory load. Feature-based maps also attempt to improve computer vision algorithms through data association, testing observed features vs. features in a pre-mapped environment. The level of accuracy must be extremely high for localization to work effectively. A weakness of feature-based maps is that it does not determine which areas are open or blocked, so it is not suitable for path planning.

**3. Topological Maps:** Focused on depicting the distance between various locations. The map is displayed in graphical format showing potential paths an AV can take. Nodes represent notable features, while arcs represent the potential paths. It is highly suited for path planning and is memory efficient.

These three types of maps are then used within AV systems to localize the vehicle. The AV will then leverage these pre-built maps to perform localization.

**Localization**

Localization can be broken down into absolute and relative localization.

**1. Absolute Localization:** Relies on (i) GPS satellites or (ii) landmarks to generate position and orientation information of the vehicle. The first method is simply through GPS technology, which we discussed is not suitable for AVs. The next method is through landmarks that are extracted from feature-based maps. This technique is more accurate and reliable than using a GPS to localize. Absolute localization through landmarks is a significant scenario where the 3D and HD maps generated by mapping companies are used

**2. Relative Localization:** Relies primarily on an AV’s sensor suite (Lidar, Radar, Camera) and a kinematic model to detect other vehicles and estimate its pose (position and orientation). It is widely used because it is collecting data in real-time and localizing the vehicle at the same time through SLAM. However, it suffers due to accumulating error over longer periods of time

A combination of these two forms of localization are used to generate the most accurate understanding of where the car is. In summary, relative localization initially localizes the AV. Over time, measurement error and drift accumulates. To minimize the localization error (i.e. distance between where the car actually is vs. where it has localized itself), the AV turns to absolute localization that has the driving region fully mapped out whether by GPS and/or 3-dimensional HD maps and acts as a variable that seeks to lower the discrepancy to a minimum.

**Simultaneous Localization and Mapping (SLAM)**

SLAM refers to solving the computational problem of constructing or updating a map in an unknown environment while simultaneously keeping track of the AV’s location within the map. It is an extremely difficult computer vision problem because it is a “chicken-or-egg” problem that is solved through optimization. The map is needed for localization and the pose estimate is needed for mapping.

Popular ways to optimize for a solution are particle filter, extended Kalman filter and GraphSLAM that use Bayes estimators. SLAM is necessary in unexplored environments where a pre-built map is not available.

