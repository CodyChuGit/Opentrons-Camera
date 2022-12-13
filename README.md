# Opentrons-Camera
An exploration of usage potential for the OT-2 onboard camera unit
This project was created in Juypter Notebook
300 image training data library can be accessed in Opentrons-Camera/Machine_Learning/


This program has 5 sub programs/actions:

1. Master_Image_Perspective_Correction:
A source image is taken from a "Master" OT-2 robot. This image serves as a ground truth that future images will reference so all collected data are aligned, regardless of variation in manufacturing camera positioning.

2. External_Image_Alignment_And_Transform_Getter:
Extract transform matrix from aligning contrast markers from future images so that collected images are aligned

3. External_Image_Transformer_and_Segmentation:
Applies the transform from "External_Image_Alignment_and_Transform_Getter" to an external image, archieves the sgemented image for manual data parsing.

4. Manual Data Parsing:
User must manually parse their collected images and place them in /Users/[username]/Projects/Machine_Learning/[subfolder] to create custom descriminators classes

5. Training_and_Learned_Model_Export:
Use tensorflow to train an existing image classifier model to determin if a future image is of one descriminator class or another.

The result is a trained model "labwareclassifier.h5", capable of classfifing an image as a "deck slot with a labware" or an "empty deck slot" and directly used. This trained model has been tested, and the results show 100% reliability in classifying these image catagories. The potential of using this feature could expand to misplaced labware detection and labware identity confirmation easily with additional collected data.


Follow this install tutorial to setup tensor flow:

https://www.tensorflow.org/install

To take images from the OT-2 camera, follow this guide:

https://support.opentrons.com/s/article/Using-the-OT-2-s-camera

This project is based on opensource projects:

https://github.com/nicknochnack/ImageClassification/blob/main/Getting%20Started.ipynb

https://learnopencv.com/image-alignment-ecc-in-opencv-c-python/

https://docs.opencv.org/4.x/examples.html
