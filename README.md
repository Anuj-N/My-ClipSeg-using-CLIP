# My-ClipSeg-using-CLIP

The aim of this project is to create a model such that it accepts a text prompt and an image as input and uses CLIP to create an embedding of the text prompt and the input image, and then train a decoder on top of this to produce a binary segmentation map. (similar to the CLIPSeg model)

Dataset being used : Custom Phrasecut Dataset (Can be found here: https://drive.google.com/file/d/1-w0_9TzFXdktLurhf0UnJ1FvA8fpxSGl/view)

I have worked on this project in the following manner:

1. First in myClip_csv_generator.ipynb, I performed the following steps:
  - Downloaded the dataset
  - Preprocess the dataset using pandas and generate csv files

2) Then in myClip.ipynb, I did the following steps:
  - Generated masks (ground truth) for the dataset images using OpenCV methods
  - Made Dataloader class and loaded the dataset
  - Made custom encoder (non-trainable) using encoder_model.py which uses CLIP's encoder functions 
  - Made custom decoder (trainable) using decoder_model.py
  - Implemented the Training Loop and ran it for 10 epochs separately for 2 different loss functions : BCE Loss and DICE Loss
  - Calculated the accuracy in 3 ways : pixel-by-pixel, iou and dice score for both
  - Tabulated the results in accuracies.pdf
