---
layout: page
title: Streamline RimNet
description: Software for clinicians
img: assets/img/rimnet.jpg
importance: 1
category: Software Development
---

Streamline RimNet was developed when I was still working as a student research assistant at the Medical Image Analysis Lab (MIAL) of the CHUV, with Dr. Meritxell Bach Cuadra.

RimNet is a deep network that predicts PRL Multiple Sclerosis lesions (also known as "rims"), from brain MRI Images. A patch of size 28x28x28 is fed in two modalities (Flair and Phase, meaning that we give the same patch, but "viewed differently" by the MRI machine), and the network predicts if the patch is or not a PRL MS lesion.

However, using the network requires a minimum of knowledge in deep learning and python, as the user needs to extract a patch from the full 3D MRI image and feed it to the network. This was a problem as most clinicians do not have coding experience, nor time to learn python. Furthermore, giving a diagnosis to the patient is a time consuming task, as several doctors need to manually search for lesions, and then compare their results.

Therefore, we decided to develop a software to help clinicians detect those lesions. The user needs to browse through a brain, and click on a potential lesion. The software then extracts the patch, feeds it to the network through docker, and returns the prediction. The network can thus act as a second opinion, instead of having another clinician analyze the same image. The software is open source and available on <a href="https://zenodo.org/records/7962482">https://zenodo.org/records/7962482</a>

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/rimnet.png" title="sessions GymRat" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
