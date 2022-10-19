# Preparing Data For Computer Vision

We want to implement a solution that prepares data for training an object detection model. The main features are as follows:

- preparation of images
- conversion of labeling data from one format to another

## Input

- images in jpg format
- image annotations in xml format (one file per image)

## Task

- read xml files
- parses the contents of these files
- resize images if dimensions exceed 800px (width) x 450px (height)
- save the final images in a dedicated folder to have a complete folder with all the images in their final version, whether they have been resized or not
- recalculates the coordinates of the bounding boxes of annotated objects to adapt them to the new dimensions of the image, if it has been resized
- composes an output file in json format and saves it to disk

## Data Format

The xml files contain the labeling data relating to a single image in Pascal VOC format. It is required to merge these records into a single file in the simplified COCO format.

## Run

The execution of the application will be done by running the entrypoint module "app.py" which will accept three parameters:

- imagedir - path to the folder with images
- xmldir - path to the folder with the xml files with the original labeling data
- outputdir - path to the output folder where the images and the produced json file will be saved
