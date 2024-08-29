---
layout: page
title: GymRat
description: Android application to track your workouts
img: assets/img/gymrat.jpg
importance: 2
category: Software Development
---

GymRat is an Android application I developed during my free time. The goal of the application is to help users track their workouts, by allowing them to create, edit, and delete exercises, workouts, and nutrition. The application also provides statistics on the user's progress, such as the evolution of the bodyweight and history of each exercise done.

The user can create a new session, depending on the workout of the day, and add exercises to it. The user can also track the nutrition (proteins and calories) for that session.

The user can add exercises to a session, and then add the number of reps and weight per set. The user can also see the history of each exercise done (ie how many sets, reps, and weight were done in the past).

Finally, the user can also add the bodyweight at each session and see the evolution of it over time.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sessions_GymRat.jpg" title="sessions GymRat" class="img-fluid rounded z-depth-1" style="max-width: 50%;" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nutrition_GymRat.jpg" title="nutrition GymRat" class="img-fluid rounded z-depth-1" style="max-width: 50%;" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/exercises_GymRat.jpg" title="exo GymRat" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/exo_history_GymRat.jpg" title="exo hist GymRat" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/weight_evolution_GymRat.jpg" title="weight GymRat" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The motivation behind developing such an application, was first for me to improve my skills in android app development and learn new libraries and tools (it was the first time for me using an internal database that does not require an internet connection, or having the data of the users stored online and potentially accessible to the database owner). I really wanted to develop an app that would be useful to me (and others as well!), and that is why I settled for a workout tracking app.

The application was developed using Kotlin, it uses a local database and doesn't require an internet connection. It is not yet available on the Play Store, but you can find the code opensource on my github <a href="https://github.com/JoeNajm/GymRat">GymRat code</a>