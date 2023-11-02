# DATA ANALYTICS WITH COGNOS
# PUBLIC TRANSPORTATION EFFICIENCY ANALYSIS

# Table of Contents
Project Overview
Motivation
Features
Data Sources
Dependencies
Getting Started
Installation
Configuration
Usage
Data Analysis
Contributing
License
# Project Overview
The Public Transportation Efficiency Analysis project is a data analysis and visualization platform that aims to assess and optimize the efficiency of public transportation systems. It leverages data from various sources to provide insights into transit operations, passenger flows, and overall system performance. This project offers tools and visualizations to support transportation authorities and urban planners in making data-driven decisions for improving public transportation.

# Motivation
Efficient and reliable public transportation is crucial for urban sustainability and quality of life. This project is motivated by the need to:

Understand how well public transportation systems are operating.
Identify areas for improvement to enhance service quality and reduce congestion.
Enable transportation authorities to allocate resources effectively.
Provide data-driven insights for decision-making and policy adjustments.
Features
# Data Integration: 
Collect and integrate data from various sources, including transit agencies, GPS trackers, and passenger feedback.

# Real-time Tracking:
Monitor and analyze real-time transit data to assess delays and service disruptions.

# Route Optimization: 
Suggest route optimizations to reduce travel times and improve passenger experience.

# Data Visualization: 
Create interactive dashboards and reports for visualizing transportation system performance.

# Performance Metrics: 
Calculate key performance indicators (KPIs) such as on-time performance, capacity utilization, and passenger satisfaction.

# Data Sources
Public transportation agencies' data feeds (GTFS, real-time data).
GPS tracking data from vehicles.
Passenger feedback and surveys.
Open data sources related to urban mobility.
# Dependencies
Before getting started, ensure that you have the following dependencies installed:

Python 3.x
Jupyter Notebook
Pandas
Matplotlib
Seaborn
Plotly
Folium
[Other project-specific libraries]
Getting Started
To set up and run the project, follow these steps:

# Installation
Clone the repository:https://github.com/KPRAHUL1/Data-Analytics-with-Cognos-Group5.git

# bash
Copy code
git clone https://github.com/your-username/public-transport-analysis.git
cd public-transport-analysis
Install project dependencies:

# bash
Copy code
pip install -r requirements.txt
Configuration
Configure the project by editing the settings file, config.yaml. Specify data sources, API keys, and other relevant parameters.
Usage
To run the project, execute the Jupyter Notebooks or Python scripts provided in the project directory. These scripts will collect, analyze, and visualize public transportation data.

# Data Analysis
The project offers various Jupyter Notebooks for data analysis and visualization. You can explore these notebooks to gain insights into public transportation efficiency and performance.

# Contributing
Contributions to this project are welcome. If you'd like to contribute, please follow our contribution guidelines.

# License
This project is licensed under the MIT License. You are free to use and modify the code as long as you follow the terms of the license.

Please replace "your-username" and adapt the content to your specific project's needs. This README file provides an overview of the Public Transportation Efficiency Analysis project, its motivation, features, data sources, dependencies, and instructions for getting started and contributing to the project.

 Dataset Link: https://www.kaggle.com/datasets/rednivrug/unisys?select=20140711.CSV
 

# GraphHopper Routing Engine
Build Status

GraphHopper is a fast and memory-efficient routing engine released under Apache License 2.0. It can be used as a Java library or standalone web server to calculate the distance, time, turn-by-turn instructions and many road attributes for a route between two or more points. Beyond this "A-to-B" routing it supports "snap to road", Isochrone calculation, mobile navigation and more. GraphHopper uses OpenStreetMap and GTFS data by default and it can import other data sources too.

# Community
We have an open community and welcome everyone. Let us know your problems, use cases or just say hello. Please see our community guidelines.

# Questions
All questions go to our forum where we also have subsections specially for developers, mobile usage, and our map matching component. You can also search Stackoverflow for answers. Please do not use our issue section for questions :)

# Contribute
Read through how to contribute for information on topics like finding and fixing bugs and improving our documentation or translations! We even have good first issues to get started.

# Get Started
To get started you can try GraphHopper Maps, read through our documentation and install the GraphHopper Web Service locally.

8.x: documentation , web service jar , announcement
unstable master: documentation
Click to see older releases
Installation
To install the GraphHopper Maps UI and the web service locally you need a JVM (>= Java 17) and do:

wget https://repo1.maven.org/maven2/com/graphhopper/graphhopper-web/8.0/graphhopper-web-8.0.jar https://raw.githubusercontent.com/graphhopper/graphhopper/8.x/config-example.yml http://download.geofabrik.de/europe/germany/berlin-latest.osm.pbf
java -D"dw.graphhopper.datareader.file=berlin-latest.osm.pbf" -jar graphhopper*.jar server config-example.yml
After a while you see a log message with 'Server - Started', then go to http://localhost:8989/ and you'll see a map of Berlin. You should be able to right click on the map to create a route.

See the documentation that contains e.g. the elevation guide and the deployment guide.

# Docker
The Docker images created by the community from the master branch can be found here (currently daily). See the Dockerfile for more details.

# GraphHopper Maps
To see the road routing feature of GraphHopper in action please go to GraphHopper Maps.

# GraphHopper Maps

GraphHopper Maps is an open source user interface, which you can find here. It can use this open source routing engine or the GraphHopper Directions API, which provides the Routing API, a Route Optimization API (based on jsprit), a fast Matrix API and an address search (based on photon). The photon project is also supported by the GraphHopper GmbH. Additionally to the GraphHopper Directions API, map tiles from various providers are used where the default is Omniscale.

All this is available for free, via encrypted connections and from German servers for a nice and private route planning experience!

Public Transit
Get started

Realtime Demo

Mobile Apps
Online
There is a web service that can be consumed by our navigation Android client.

android navigation demo app

# Offline
Offline routing is no longer officially supported but should still work. See version 1.0 with still an Android demo and this pull request of the iOS fork including a demo for iOS.

simple routing

# Analysis
Use isochrones to calculate and visualize the reachable area for a certain travel mode

Isochrone Web API
Isochrone API image

Shortest Path Tree API
high precision reachability image

To support these high precision reachability approaches there is the /spt endpoint (shortest path tree). See #1577

Map Matching
There is the map matching subproject to snap GPX traces to the road.



# Technical Overview
GraphHopper supports several routing algorithms, such as Dijkstra and A* and its bidirectional variants. Furthermore, it allows you to use Contraction Hierarchies (CH) very easily. We call this speed mode; without this CH preparation, we call it flexible mode.

The speed mode comes with very fast and lightweight (less RAM) responses and it does not use heuristics. However, only predefined vehicle profiles are possible and this additional CH preparation is time and resource consuming.

Then there is the hybrid mode which also requires more time and memory for the preparation, but it is much more flexible regarding changing properties per request or e.g. integrating traffic data. Furthermore, this hybrid mode is slower than the speed mode, but it is an order of magnitude faster than the flexible mode and uses less RAM for one request.

If the preparations exist you can switch between all modes at request time.

Read more about the technical details here.

# License
We chose the Apache License to make it easy for you to embed GraphHopper in your products, even closed source. We suggest that you contribute back your changes, as GraphHopper evolves fast.

# OpenStreetMap Support
OpenStreetMap is directly supported by GraphHopper. Without the amazing data from OpenStreetMap, GraphHopper wouldn't be possible at all. Other map data will need a custom import procedure, see e.g. Ordnance Survey, Shapefile like ESRI or Navteq.

# Written in Java
GraphHopper is written in Java and officially runs on Linux, Mac OS X and Windows.

# Maven
Embed GraphHopper with OpenStreetMap support into your Java application via the following snippet:

<dependency>
    <groupId>com.graphhopper</groupId>
    <artifactId>graphhopper-core</artifactId>
    <version>[LATEST-VERSION]</version>
</dependency>
See our example application to get started fast.

# Customizable
You can customize GraphHopper with Java knowledge (with a high and low level API) and also without Java knowledge using the custom models.

# Web API
With the web module, we provide code to query GraphHopper over HTTP and decrease bandwidth usage as much as possible. For that we use an efficient polyline encoding, the Ramer–Douglas–Peucker algorithm, and a simple GZIP servlet filter.

On the client side, we provide a Java and JavaScript client.

# Desktop
GraphHopper also runs on the Desktop in a Java application without internet access. For debugging purposes GraphHopper can produce vector tiles, i.e. a visualization of the road network in the browser (see #1572). Also a more low level Swing-based UI is provided via MiniGraphUI in the tools module, see some visualizations done with it here. A fast and production ready map visualization for the Desktop can be implemented via mapsforge or mapsforge vtm.

# Features
Here is a list of the more detailed features:

Works out of the box with OpenStreetMap (osm/xml and pbf) and can be adapted to custom data
OpenStreetMap integration: stores and considers road type, speed limit, the surface, barriers, access restrictions, ferries, conditional access restrictions, ...
GraphHopper is fast. And with the so called "Contraction Hierarchies" it can be even faster (enabled by default).
Memory efficient data structures, algorithms and the low and high level API is tuned towards ease of use and efficiency
Pre-built routing profiles: car, bike, racing bike, mountain bike, foot, hike, motorcycle, wheelchair, ...
Customization of these profiles are possible and e.g. get truck routing or support for cargo bikes and many other changes
Provides a powerful web API that exposes the data from OpenStreetMap and allows customizing the vehicle profiles per request. With JavaScript and Java clients.
Does map matching
Supports public transit routing and GTFS.
Offers turn instructions in more than 45 languages, contribute or improve here
Displays and takes into account elevation data
Alternative routes
Turn costs and restrictions
Country specific routing via country rules
Allows customizing routing behavior using custom areas
The core uses only a few dependencies (hppc, jts, janino and slf4j)
Scales from small indoor-sized to world-wide-sized graphs
Finds nearest point on street e.g. to get elevation or 'snap to road' or being used as spatial index (see #1485)
Calculates isochrones and shortest path trees
Shows the whole road network in the browser for debugging purposes ("vector tile support") #1572
Shows details along a route like road_class or max_speed ("path details") #1142
Written Java and simple start for developers via Maven.
