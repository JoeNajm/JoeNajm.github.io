---
layout: page
title: ApiZoom – deep learning to quantify the Varroa parasite in honey bee hive images
description: Deep learning to quantify the Varroa parasite in honey bee hive images
img: assets/img/yolov5_varroa.png
importance: 1
category: Machine Learning
---

ApiZoom is a project I worked on for my Bachelor thesis at EPFL (with Prof. Jean-Philippe Thiran and his lab LTS5). The goal of the project was to train a deep learning model to automatically detect varroa mites on honey bees in images. ApiZoom aim to develop a tool to help beekeepers monitor the health of their hives.

Varroa mites are a major threat to honey bees, as they feed on the bees' hemolymph, weakening the bees and transmitting diseases. The mites are visible to the naked eye, but their detection is time-consuming and requires expertise. The current way of checking the health of a hive is to place a board on the bottom and count manually count how many mites are there. This task is not only extremely time consuming, but very difficult as the board is quite big and the mites are small.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/varroa.jpg" title="varroa" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/board.jpg" title="board hive" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The goal of ApiZoom was to develop a tool that could automatically detect the mites in images, making the process faster and more accessible to beekeepers. YOLOv5 was chosen as it was the state-of-the-art at the time, easy to finetune, highly performant and most importantly fast (in order for the bee-keeper to receive a feedback quickly). The model was then integrated into a web application, where the user could upload an image and receive the number of mites detected (<a href="https://www.apizoom.app/">https://www.apizoom.app/</a>).

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/yolov5_varroa.jpg" title="yolov5" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

It was my first experience with deep learning, and I learned a lot about the process of training a model. This experience paved the way for my future projects in the field of computer vision and deep learning, as well as initiating a strong attraction to Machine Learning.
