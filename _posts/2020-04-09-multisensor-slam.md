---
layout: post
title: Multisensor SLAM for autonomous ferry
category: SF
---
## Background
The navigation of the autonomous ferry MilliAmpere is currently based on GNSS. For improved robustness, especially in docking scenarios,
this system should be complemented by navigation done purely by means of onboard sensors. 
The ferry is currently equipped with lidar, radar (active sensors), optical cameras and infrafred cameras (passive sensors). 


Previous specialization and MSc projects have investigated the possibility of lidar-based or visual SLAM and localization for MilliAmpere. Marius Ødven conducted data recording experiments with the Velodyne Puck lidar mounted onboard MilliAmpere in Brattørabassenget and investigated several open-source methods for lidar-SLAM. Nicholas Dalhaug investigated localization by means of particle filters using the same data set. Even Skjellaug evaluated several feature extractors and descriptors on this data set, and demonstrated that accuracy similar to standard GNSS accuracy could be maintained for several minutes by means of laser odometry. In his MSc project he is currently working on factor graph SLAM using the ISAM2 framework on this data set. In parallell with this, Hallvard Laupsa Fosso has used the visual slam method ORB-SLAM on infrared data from MilliAmpere's on-board sensor rig. 

Building upon these works, an intriguing possibility is to use multi-sensor SLAM methods for navigation of MilliAmpere. There are several reasons why this is of interest. In general, a multi-sensor system can be expected to show greater resilience to sensor faults and adverse weather conditions than a single-sensor system. While visual SLAM currently is very popular and dominates the research frontier in SLAM, a problem with visual SLAM is that landmarks are hard to initialize when the ferry is stationary, since motion is needed to estimate the scale. However, if data from a lidar or radar are associated to the visual data, then this can be done. On the other hand, the richness of visual data may also be useful to improve the robustness of SLAM using active sensors. 

The research literature is surprisingly devoid of results on SLAM for maritime surface vessels, and also of results on multi-sensor SLAM. However, the factor graph libraries (GTSAM, G2O, etc) that are used in state-of-the-art SLAM methods are of a general nature, and can probably be adapted to handle all the data sources that are of relevance for localization of MilliAmpere.  	


|<img src="{{site.url}}/assets/occupancybratt.png" width="690"> | 
| Occupancy grid for the Brattøra pool generated by lidar data recorded onboard Milliampere (Dalhaug 2019). | 



## Scope
The goal of this combined specalization and Master's project is to develop a multi-sensor SLAM method for MilliAmpere that can be used for real-time localization in the case of poor or missing GNSS data. 

## Proposed Tasks for the 5th year project

1. Conduct a literature survey on the state-of-the-art in SLAM using lidars and other range finders.
2. Conduct a literature survey on methods for localization relative to known landmarks and maps. 
3. Implement a chosen SLAM method on data recorded using the lidar onboard Milliampere. 
4. Implement a chosen localization method on data recorded using the lidar onboard Milliampere. 
5. Compare the performance of the two approaches in the project report. 

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2018. Key challenges that should be addressed are expected to be data association, integration with inertial navigation system and real-time implementation. 

## Contact
For more information, contact main supervisor [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo)

## References

* Ødven, M. (2019): “[Lidar-based SLAM for Autonomous Ferry](http://folk.ntnu.no/edmundfo/msc2019-2020/MasterFinalReducedMarius.pdf)”, MSc thesis, NTNU
* Dalhaug, N. (2019): “Lidar-based localization for autonomous ferry”, MSc thesis, NTNU, in writing. 