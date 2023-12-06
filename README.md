# Edge TPU Object Tracker Example

This repo contains an edited version of [Google Coral Tracking Demo](https://github.com/google-coral/example-object-tracker) to present the number of people in a frame. Utilizes [PySimpleGUI](https://www.pysimplegui.org/en/latest/) and


## Installation

1.  First, be sure you have completed the [setup instructions for your Coral
    device](https://coral.ai/docs/setup/). If it's been a while, repeat to be sure
    you have the latest software.

    Importantly, you should have the latest TensorFlow Lite runtime installed
    (as per the [Python quickstart](
    https://www.tensorflow.org/lite/guide/python)).

2.  Clone this Git repo onto your computer:

    ```
    mkdir google-coral && cd google-coral

    git clone https://github.com/disisid17/Person-tracker.git

    cd Person-tracker/
    ```

3.  Download the models:

    ```
    sh download_models.sh
    ```

    These models will be downloaded to a new folder
    ```models```.


Further requirements may be needed by the different camera libraries, check the
README file for the respective subfolder.

## Contents

  * __gstreamer__: Python examples using gstreamer to obtain camera stream. These
    examples work on Linux using a webcam, Raspberry Pi with
    the Raspicam, and on the Coral DevBoard using the Coral camera. For the
    former two, you will also need a Coral USB Accelerator to run the models.

    This demo provides the support of an Object tracker. After following the setup 
    instructions in README file for the subfolder ```gstreamer```, you can run the tracker demo:

    ```
    cd gstreamer
    python3 detect.py --tracker sort
    ```

## Models

For the demos in this repository you can change the model and the labels
file by using the flags flags ```--model``` and
```--labels```. Be sure to use the models labeled _edgetpu, as those are
compiled for the accelerator -  otherwise the model will run on the CPU and
be much slower.


For detection you need to select one of the SSD detection models
and its corresponding labels file:

```
mobilenet_ssd_v2_coco_quant_postprocess_edgetpu.tflite, coco_labels.txt
```


