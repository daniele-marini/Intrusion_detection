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

## Instruments

To accomplish the detection of the intruder different techniques have been employed:

* Background extraction through interpolation (mean or median)
 * The median turns out to be more effective for this particular video, as the person is constantly moving, therefore pixel intensities, across the frames, which have high variance won't be picked as eligible values.
* Frame difference with extracted background, trying three distances:
  * Manhattan distance.
  * Euclidean distance.
  * Maximum distance.
* Morphology operators to improve the mask quality (binary image obtained from difference between frame and background):
  * Opening, to get rid of noise, consisting of smaller blobs.
  * Closing, to fill holes in the detected intruder.
* Contour extraction:
  * Find and draw contours
* Features extraction:
  * Area
  * Perimeter

## Results

As result we get a video with the contour of the intruder highlighted and the contour of the object that have been moved from him.
Also, we generate a txt file that include identified objects information:
* Frame number
* Number of identified objects
* Identifier, area, perimeter and label of identified object 

![res (1)](https://user-images.githubusercontent.com/88623698/215541389-c9bea3c7-ac8f-4270-8e8c-043129da6ec4.gif)
