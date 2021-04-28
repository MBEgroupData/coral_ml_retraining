This repository contains a version of the MobileNet model that has been optimized to run
on the coral device.

First clone this repository and cd into the cloned folder. 

To retrain this model so it only will classify the image classes that we specify. Run this command in
a terminal:
```
  python3 imprinting_learning.py \\
  --model_path mobilenet_edgetpu.tflite \\
  --data open_image_v4_subset \\
  --output retrained_imprinting_model.tflite
```
This will retrain the MobileNet model to identify the classes that are specified
by the directories in the open_image_v4_subset folder. 

To test the retrained model run:
```
python3 classify_image.py \\
--model retrained_imprinting_model.tflite \\
--label retrained_imprinting_model.txt \\
--image test_images/cat.jpg
```

To add your own class to train
just create a folder inside of the open_image_v4_subset, and put your images in that folder.
