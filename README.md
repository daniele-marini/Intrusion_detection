# Intrusion_detection

Project work for the "Image Processing and Computer Vision" course of the Artificial Intelligence Master's Degree at University of Bologna

## Authors:

* Daniele Marini
* Giuseppe Tanzi
* Iulian Zorila

## Problem 

The task is about detecting objects (intruders) that do not belong to a static reference scene (background) and establish which of such objects are persons.
This is achieved by background subtraction and blob labeling process

## Data

Starting from a given video:
* 12 frame/s (total duration is about 41 secs)
* 320x240 pixels
* 8 bit/pixel (256 gray levels)
* The sequence is compressed by the Radius Cinepak CODEC.

Whereby a person moves at different speed and is shown in various sizes.
In the last part the subject steals an object belonging to the scene,replacing it with another one.
The scene is static and this is precisely the condition which allows to extract the background via interpolation.
