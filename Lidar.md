---
type: page
title: LiDAR
---

**Definition:** 

LiDAR stands for light detection and ranging.

**How LiDAR Works:** 

A LiDAR instrument fires pulses of laser light rapidly, up to 150,000 pulses per second. The pulses of light hit objects and bounces back, which are recorded by the sensor. The LiDAR instrument is able to compute the distance between itself and its surroundings with high accuracy. As the LiDAR instrument constantly fires out laser pulses, it is able to create a point cloud, which is an accurate, dense 3D map of the area it is measuring.

![lidar_1](/assets/pictures/lidar_1.jpg){:class="img-responsive"}*Here is a point cloud captured from a single frame of Luminar’s lidar sensor. This output allows the AV to understand its surroundings and their distances/angles as well as the velocity of the objects around it.*

**Characteristics of LiDAR:**

**1. Active Sensing:** LiDAR is an active sensing system, which is in contrast to a passive sensing system. This is because it emits laser beams and detects the reflected light.

**2. Highly Accurate:** LiDAR provides extremely precise measurements to an accuracy of ±2 centimeters

**3. Day and Night Usage:** LiDAR is able to operate both at day and at night. However, it is does not work well when the sun is at a high angle or there are huge reflections as the instrument depends on reflection.

**4. Detection requires line of sight:** LiDAR is affected by anything that may affect lasers from hitting its surroundings (i.e. fog, rain). Multiple lasers make its measurements more reliable in poor weather conditions.

**How far can LiDAR measure?**

Current LiDAR can measure up to approximately 200 meters depending on the LiDAR instrument. It is expected to attain 300-400 meters in the future.

**LiDAR Production**

As LiDAR is increasingly used for testing of autonomous vehicles, suppliers have faced significant challenges with delivering LiDAR at scale at a low cost, resulting in production bottlenecks. Due to these capacity constraints, companies have developed their LiDAR in-house (i.e. Waymo) or acquired LiDAR companies (i.e. Cruise acquiring Strobe). Due to the supply constraints of LiDAR, it has historically been extremely expensive to purchase LiDAR instruments, though price is expected to drop significantly to <$500 from $70,000+.

**Solid State LiDARS vs. Rotating Mirror LiDARS**

The autonomous driving industry has been moving towards implementing solid state LiDAR because it is cheap, robust and compact. However, solid state LiDARs are still primarily in the later stages of design and prototyping phase as opposed to production phase. One of the downsides to solid state LiDAR is that the field of view is smaller (generally <120 degres), meaning it sees less than its predecessor rotating mirror LiDARs. However, by placing several solid state LiDARs on different areas of the vehicle, it can fuse an image matching that of the bulky rotating mirror LiDAR. Rotating mirror (mechanical spinning) LiDARs, characterized by their dome shape and rapid spinning, were invented in the mid-2000’s by Velodyne. Given their early arrival, they have been extremely popular on current autonomous vehicles in testing. Nevertheless, due to their poor form factor and high cost (up to $70,000+), the likely outcome is that autonomous driving companies will transition to solid state LiDARs.


![lidar_2](/assets/pictures/lidar_2.jpg){:class="img-responsive"}*Solid State Lidar (Velodyne Velarray)*

![lidar_3](/assets/pictures/lidar_3.png){:class="img-responsive"}*Various Velodyne LiDAR devices*
