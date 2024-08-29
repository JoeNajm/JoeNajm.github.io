---
layout: page
title: EPFL Racing Team
description: Driverless Perception
img: assets/img/lrt.jpg
importance: 1
category: Self-driving Car
related_publications: true
---

The EPFL Racing Team is a student association at the École Polytechnique Fédérale de Lausanne (EPFL) that designs an electric and autonomous racing car every year, and competes in the Formula Student competition. The team is composed of students from various fields of study, such as mechanical engineering, electrical engineering, computer science, and management. The team is divided into several subteams, each responsible for a specific part of the car, such as the chassis, the powertrain, the suspension, the aerodynamics, the driverless system, and the business plan.

I joined the team in September 2021 as a perception engineer in the driverless subteam, where the main task is to develop realtime algorithms that detect and estimate accurately the distance of objects (yellow and blue cones) to the car. The perception system is composed of several sensors: a monocular camera and a LiDAR. and the algorithms, based on Machine Learning are implemented in Python. The perception system is a crucial part of the driverless car, as it provides the necessary information to the planning and control algorithms to make the car drive autonomously.

During my second year in the team, I was promoted to the role of perception group leader, where I was responsible for the development of the perception system, and its integration into the rest of the pipeline (using ROS 2). It was during my second year that the team managed to make the car drive by itself for the first time ever! Although the car was moving at a relatively slow speed (5 m/s), it was nevertheless an incredible and satisfying achievement. 

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lrt_dv_squad.jpeg" title="dv squad" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        <video class="tutorial_vid" width="220" height="140" autoplay="autoplay" loop> 
          <source src="assets/img/vaudoise.mp4" type="video/mp4" /> 
       </video>
    </div>
</div>
<div class="caption">
    On the left is the amazing driverless team, while on the right is the car driving autonomously!
</div>

My team and I developed three pipelines for the perception system: a monocular pipeline, a LiDAR pipeline, and a fusion pipeline. Depending on the event, only one pipeline would run, however, in case of sensor failure, the working pipeline would automatically switch, in order to continue the event (ie, if the fusion pipeline was running and the LiDAR failed, the monocular pipeline would take over). 

The monocular pipeline: the monocular pipeline was based on a YOLOv7 object detection algorithm that was finetuned to simultaneously detect, classify but also find 7 keypoints on the cones. For each cone, the distance was estimated using the keypoints and a PnP algorithm (based on the camera intrinsics and the known geometry of the cone). 

The LiDAR pipeline: the LiDAR pipeline was based on clustering the LiDAR  pointcloud to extract the cones. First, a ground removal was done (Ransac is the track was flat, otherwise another more adapted ground-bin based algorithm), then objects that were too far, near, big, high, low ... were removed, in order to have only the cones remaining on the pointcloud. The cones were then extracted using a DBSCAN algorithm, and the distance was estimated using the median of each cone.

The fusion pipeline: the fusion pipeline was based on the monocular and LiDAR pipelines. The monocular pipeline would detect the cones on the image using YOLOv7, meanwhile the ground was removed from the LiDAR pointcloud. Knowing the intrinsics of the camera and extrinsics between the LiDAR and camera, the points of the remaining pointcloud would be projected on the image, and using the bounding boxes of the YOLOv7, the points that were inside the bounding boxes would be extracted. The distance was then estimated using the median of the points.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vision_sensors.png" title="dv squad" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/vsv_dv.mp4" title="vsv" class="video" %}
    </div>
</div>
<div class="caption">
    On the left is an overview of the pipelines, and on the right the pipelines in action!
</div>

My team and I encountered major problem all throughout the development process, but managed to find solutions. Indeed, it was the first time anyone of us had to use ROS 2, we had to find a way to synchronize the sensors (otherwise the fusion would not work), make important performance compromises in order to respect the realtime constraints (some of the famous libraries were too slow), find extremely accurate intrinsics and extrinsics, correct the ego-motion of the LiDAR ...  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
