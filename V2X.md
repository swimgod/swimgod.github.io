---
layout: page-2
title: V2X
---

**Definition:**

V2X stands for Vehicle-to-everything. V2X encompasses technology related to vehicle communication with other vehicles, networks, infrastructure and pedestrians. For the purposes of autonomous driving, it provides an additional layer of data and safety by supplementing the data gathered by vehicles through their sensor suite.

**Why is V2X important?**

For autonomous vehicles, V2X allows the vehicle to “see” outside of its own field of vision. This is especially important in hazardous situations to provide incremental reaction time for the AV to react. Outside of hazardous situations, V2X systems can provide the vehicle and its passengers with traffic updates and up-to-date weather alerts, increasing transportation system efficiency. V2X technology will also provide convenience for vehicles by integrating a payment sysetm for fuel, tolls, parking, etc.

**How prevalent is V2X today?**

The market for V2X is still nascent for a number of reasons. First of all, vehicles need to be built in with V2X technology. The deployment within vehicles on the road will be a slow process as it takes ~15 years to turn over an entire vehicle fleet, a number that has been increasing over the past few decades. On the other hand, arguably the first widespread use case of V2X will be communication with traffic systems will require an overhaul of current traffic systems, which will need to be updated to incorporate V2X systems.

In my opinion, V2V (Vehicle-to-vehicle) and V2P (Vehicle-to-pedestrian) will come after V2I (Vehicle-to-infrastructure) based on my observations. My reasoning is that autonomous driving companies will operate in geofenced areas that will likely be on the forefront of implementing traffic technology with V2X capabilities. V2V would seem to lack reliability until a majority of vehicles have V2X technology, and there isn’t a clear market for V2P yet. In summary, there is a lot of potential for V2X over the next few decades, but little is in the market right now.

**Multiple Key Technologies for V2X**

**DSRC based on IEEE 802.11p and ITS-G5 (WiFi)**

DSRC is “a two-way short-to-medium-range wireless communications capability that permits very high data transmission critical in communications-based active safety applications.” In 1999, the FCC set aside bandwidth to be used specifically for vehicle-related safety and mobility systems. It is designed to adhere to 802.11p, a set of standards defining wireless access in vehicular environments. The 802.11 standards essentially describe WiFi based technology.

Recent News: In November 2017, the Trump administration quietly dropped plans to mandate DSRC for vehicles, creating opportunity for 5G and cellular technologies. Over the past several years, there has been controversy between the usage of DSRC vs cellular technology, and many argue that the government should not determine the technology of choice.

**C-V2X**

Cellular V2X was standardized by the 3GPP in 2016 under LTE Release 14. It is expected to offer a performance improvement over 802.11p by providing “up to a few additional seconds of alert latency and 2x range.” The release of 5G technology will drive significantly increased speed and low latency.

Cellular V2X breaks up into two separate interfaces:

**1. Direct Communications (PC5 interface):** Encompasses high-reliability and low latency services including V2V, V2I and V2P. It generally does not require assistance for a cellular network.

**2. Network Communications (Uu interface):** Encompasses higher latency-tolerant use cases using wide area network communications for V2N (Vehicle-to-network) use cases.

**Commentary on DSRC vs C-V2X technologies**

The debate on which technology will win out is impossible to determine at this time given the market for V2X is highly under-penetrated and very early. The likely outcome may very well be a combination of the two technology, but I believe it is anyone’s guess right now. Both sides have issued reports that their technology is more reliable than the other, but important determining factors include 5G rollout, performance benchmarking, security, etc. One prominent proponent of C-V2X to note is Qualcomm, which plays a key role in both technologies and their arguments are helpful to read if you are interested.

**Use Cases of V2X Technology**

According to the National Connected Vehicle Field Infrastructure Footprint Analysis report conducted by the American Association of State Highway and Transportation Officials, a combination of cellular and WiFi (DSRC) technology is expected to include:

1. Roadside communications equipment and enclosures, mountings, power, and network backhaul

2. Traffic signal controller interfaces for applications that require signal phase and timing data

3. Systems and processes required to support management of security credentials and ensure a trusted network

4. Mapping services that provide highly detailed roadway geometries, signage, and asset locations for the various connected vehicle applications

5. Positioning services for resolving vehicle locations to high accuracy and precision

6. Data servers for collecting and processing data provided by vehicles and for distributing information, advisories, and alerts to users