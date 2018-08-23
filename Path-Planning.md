---
layout: page-2
title: Path Planning
---

![path_planning_1](/assets/pictures/path_planning_1.jpg){:class="img-responsive"}*Futuristic representation of an AV determining the best path forward*

**Definition:**

Path planning involves the decision making process of determining the best possible route for an AV while maneuvering a dynamic landscape of cars and objects.

**Why is path planning important?**

Path planning is the step that determines how a car will navigate around other traffic. The pre-requisites for path planning include prior steps computer vision, sensor fusion and localization. Through these first three categories, the vehicle has developed an understanding of the environment around it, but we have not yet figured out how to get to where we want to get and path planning is that essential step.

**The Path Planning Problem**

The path planning problem can be broken down into three steps:

**1. Environment Prediction:** understanding the projected trajectories of dynamic landscape

**Example:** Imagine you are about to drive through a green light. You are 50 feet from the light when a pedestrian begins jaywalking while looking down at his/her phone. Through environment prediction, the vehicle will anticipate the oncoming jaywalker and slow to a stop. This is a simple case of environment prediction, but in reality, there are many other scenarios that may involve multiple developing situations that the AV must adequately anticipate.

**2. Behavior Planning:** suggests what behavior the vehicle should take using the information extracted from environment prediction

**Example:** Once the vehicle has developed its own understanding of its surroundings and where it believes vehicles and pedestrians are moving, the vehicle now needs to decide what action to take to move it towards its destination.

**3. Trajectory Generation:** generates the actual path that the vehicle will take based on the suggested behavior and current pose and orientation of the vehicle

**The Easy Part**

Within the path planning problem, the trajectory generation step is understood because it is a straightforward problem that can be solved with a little bit of physics and math.

**The Difficult Part**

On the other hand, the prediction steps are extremely difficult. With environmental prediction, there are a plethora of ways vehicles or pedestrians can demonstrate their intent. For humans, we are often able to pick up nonverbal cues or track a dynamic, rapidly changing situation, but even so, we are often wrong, which is why accidents happen. For robots, this is extremely difficult to program, and this is a significant challenge for engineers to interpret a dynamic scene and predict what is going to happen. In addition, behavior planning is also extremely difficult. First of all, it is dependent on the environmental prediction step causing much uncertainty. One classic example is a very densely populated street during rush hour where there is a pedestrian crosswalk. If the autonomous vehicle is not assertive, it may not be able to cross the crosswalk for a long time. Being able to determine appropriate behavior is difficult. Another classic example is when an autonomous vehicle is bracing for collision, but has the option to swerve and crash into a pole vs. running into a grown man. This has philosophical/ethical implications as well, which makes the problem complex along with the uncertainty involved.

**A Brief on Implementation**

This is a little bit on the technical side, but I do think it is interesting to touch upon. To think about solving the path planning problem, there is a starting point and a goal (end) point. There are a number of ways to think about getting from the starting point to the goal. I will not get into detail on what the techniques are, but they generally include a cost function and an estimated distance to a goal in order to figure out the shortest path based on the assumptions provided. All of the algorithms revolve around different ways of implementing these functions to create a systematic path finding approach. If you are interested, check out A* Search (which I learned through Udacity’s Intro to Self-Driving Cars Course), which is a commonly taught search algorithm for finding optimal path.

**Path Planning Considerations**

1. Data Collection: what data to collect from sensors?
2. Data Cleaning: what details are relevant to the problem?
3. Prediction Steps: how to navigate uncertainty around environment prediction and behavior planning?