---
layout: page
title: BeaverNav
img: assets/beaver_nav/header.png
description: Dec 2022
importance: 1
category: fun
related_publications: false
---

### Problem
MIT is a large campus with thousands of rooms/hallways/buildings/staircases/elevators. Finding one’s way around campus can be difficult and daunting.

### Our Solution

Indoor navigation for MIT’s campus: Enables users to navigate between rooms, provides routes from start destination to end destination

**Note this is still a work in progress & is not yet a live website**


<div class="row">
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/beaver_nav/AIM Labs Demo 2-2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
</div>
<div class="caption">
    Navigation inside a building
</div>

<div class="row">
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/beaver_nav/AIM Labs Demo 2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
</div>
<div class="caption">
    Navigation between buildings 
</div>

We built this using the following pipeline:
1. Scrape Floor Plans from MIT website, and process into images
2. Extract key information (room coordinate locations & names) via pre-trained neural network text detection and recognition models (EAST, Easy OCR).
3. Remove all doors & text from the floorplans & downsample (reduce resolution)
4. Create a graph treating every pixel as a node in the graph
5. Condense graph offline by running an additional all pairs shortest paths algorithm (APSP) & use A* for online planning
6. Create an “abstracted graph” of MIT’s campus using elevators, staircases, entry-exits between buildings


<div class="row">
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/beaver_nav/AIM Labs Demo 2-3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
</div>
<div class="caption">
    High-Level Graph
</div>


More in-depth explanation can be found below


## [<u>Code</u>](https://github.com/kw7243/BeaverNav)

## [<u>Demo</u>](</assets/beaver_nav/demo_vid.mov>):
<div class="row">
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        <iframe src="/assets/beaver_nav/demo_vid.mov" width="100%" height="600px"></iframe>
    </div>
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
</div>

## [<u>Project Presentation</u>](</assets/beaver_nav/AIM Labs Demo 2.pdf>):
<div class="row">
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        <iframe src="/assets/beaver_nav/AIM Labs Demo 2.pdf" width="100%" height="600px"></iframe>
    </div>
    <div class="col-sm-1 mt-3 mt-md-0">
    </div>
</div>


