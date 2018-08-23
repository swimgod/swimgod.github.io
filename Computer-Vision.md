---
layout: page-2
title: Computer Vision
---

**Definition:** 

Computer vision works at the intersection of artificial intelligence and computer science dealing with how computers are used to understand digital images or videos.

**Overview of Computer Vision:**

Computer vision can be broken down into three stages:

**1. Image Acquisition**

**2. Image Processing**

**3. Image Analysis and Understanding**

The goal with computer vision is essentially to emulate a human’s ability to perceive, process and analyze images.

Image Acquisition
Image acquisition is the process of capturing the analog world and converting it into binary data (digital images) that a computer can interpret. This initial step of computer vision of acquiring images is where scientists and engineers have had great success in creating sensors and image processors that reproduce what the human eye can see and often exceeds the human eye’s abilities.  Within autonomous vehicles, an image is acquired and fused through sensor fusion (discussed in the next article).

Image Processing
The next component in the computer vision pipeline is pre-processing and performing low-level processing on the images as a way to prepare the digital image for analysis. For a computer, the way that it interprets an image is in 0’s and 1’s, otherwise known as binary data, similarly to how we communicate with words. Certain machine learning algorithms are applied to the binary data (0’s and 1’s) in order to figure out low-level information on parts of the image. Data received from the image acquisition phase needs to be cleaned, meaning the image data must be standardized.

Example: Let’s use an example of an autonomous driving system we are trying to train to recognize stop signs. Images that are passed through the network will be in different lighting conditions and the pictures will come in different sizes. The way that we can train an autonomous driving system is to standardize the images. Examples of standardization include cropping the image, changing the image into grayscale or resizing the image to your desired dimensions.

Following this pre-processing process, low-level processing algorithms can be used to gather information on the image. 

Some of these algorithms include:

1. Feature extraction

2. Edge detection

3. Segmentation

4. Classification

Image Analysis and Understanding
The last component is performing detailed analysis on the data in order to generate a decision. This step is by far the most difficult one that scientists and engineers struggle with today. Within this step, high-level algorithms are applied using the image data and low-level information from the prior step. 

Examples of high-level image analysis include:

1. 3D scene mapping

2. Image restoration

3. Object recognition and identification

4. Motion analysis

How does Computer Vision Work?
Today, computer vision relies on enormous amounts of data that are passed through the computer to train it to better analyze images. For an autonomous driving system to recognize a stop sign in the scenario discussed above, a computer vision expert would pass through thousands and thousands of images of stop signs to train the system. Then it would test the autonomous driving system over another large dataset to see if it could accurately determine a stop sign in hopes of achieving close to 100% accuracy, especially focusing on potential edge cases; images that cause the system to classify the image incorrectly. To understand computer vision better, it is also important to understand artificial intelligence and its subsets (machine learning, deep learning) because they come hand-in-hand.

What are the applications of Computer Vision outside of Autonomous Driving?
1. Autonomous Robots

2. Image Restoration

3. Augmented Reality

4. 3-D Printing

5. Medical Imaging

What are the Challenges of Computer Vision?
The largest challenges of computer vision in autonomous driving are object recognition and scene understanding. 

Here are a few potential reasons why:

1. Data received by an autonomous vehicle is often noisy. One example is the sun is extremely bright casting huge reflections and causing the sensors to gather data with greater error. An instance like this is called an edge case where the autonomous driving system may not be equipped to handle an extreme situation like this. The reality of autonomous driving is that there are an enormous amount of edge cases that arise all the time that need to be solved, which is why computer vision engineers are in such high demand.
2. Limited computing ability. Cars move extremely quickly and the difference between avoiding an accident and getting into an accident could be a matter of a split second. As a result, cars need to locally compute and make decisions, which mean autonomous vehicles must have significant processing power and memory. While processing power has increased exponentially as a result of Moore’s Law, computing ability remains a potential concern to watch.