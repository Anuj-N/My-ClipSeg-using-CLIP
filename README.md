# My-ClipSeg-using-CLIP

The aim of this project is to create a model such that it accepts a text prompt and an image as input and uses CLIP to create an embedding of the text prompt and the input image, and then train a decoder on top of this to produce a binary segmentation map. (similar to the CLIPSeg model)

Dataset being used = Custom Phrasecut Dataset (Can be found here: https://drive.google.com/file/d/1-w0_9TzFXdktLurhf0UnJ1FvA8fpxSGl/view)

Till now, I have tried to attempt work on this project in the following manner:

1) First in myClip_csv_generator.ipynb, I did the following steps:
  a) Downloaded the dataset
  b) Preprocess the dataset using pandas and generate csv files

2) Then in myClip.ipynb, I did the following steps:
  a) Generated masks for the dataset using OpenCV
  b) Made custom encoder (non-trainable) using CLIP's functions
  c) Made custom decoder (trainable)
  d)Made Dataloader class and loaded the dataset
  e)Implemented the Training Loop
