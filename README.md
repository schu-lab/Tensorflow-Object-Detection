# TensorFlow-Object-Detection
TensorFlow-Object-Detection using Python3, TensorFlow, OpenCV, and dataset (.jpg and .xml [Pascal VOC format])

<p align="center">
  <img src=https://github.com/schu-lab/Tensorflow-Object-Detection/blob/main/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f6a7131765a436555754d434e47716c4e31392f67697068792d646f776e73697a65642d6c617267652e676966.gif alt="animated" height="400" />
</p>

[Project to utilize TensorFlow to detect objects]<br /> 
Slidedeck: https://github.com/schu-lab/TensorFlow-Object-Detection/blob/main/Chu-Object-Detection-Presentation.pptx

References: 
* https://www.tensorflow.org/
* https://sci2s.ugr.es/weapons-detection
* https://github.com/tensorflow/examples
* https://www.digikey.com/en/maker/projects/how-to-perform-object-detection-with-tensorflow-lite-on-raspberry-pi/b929e1519c7c43d5b2c6f89984883588
* https://colab.research.google.com/github/khanhlvg/tflite_raspberry_pi/blob/main/object_detection/Train_custom_model_tutorial.ipynb
* https://dasci.es/transferencia/open-data/24705/
* https://github.com/tzutalin/labelImg

Data Sets:
* [Handgun Images] https://sci2s.ugr.es/sites/default/files/files/TematicWebSites/WeaponsDetection/BasesDeDatos/WeaponS.zip
* [Handgun Annotation] https://sci2s.ugr.es/sites/default/files/files/TematicWebSites/WeaponsDetection/BasesDeDatos/WeaponS_bbox.zip
* [Android Toys Data Set - .jpg + .xml (Pascal VOC)] https://storage.googleapis.com/download.tensorflow.org/data/android_figurine.zip
 
# Hardware Required:
<div align="center">
  <img src= "https://github.com/schu-lab/TensorFlow-Object-Detection/blob/main/Pi-Camera.jpg" | height="300")>
  <img src= "https://github.com/schu-lab/TensorFlow-Object-Detection/blob/main/Raspberry-Pi.jpg" | height="300")>
  <br /><br />
</div>
Major Components (1) Raspberry Pi 4GB, (2) PiCamera 2018 v.1.0, (3) 6mm CS Lens, & (4) Camera Stand for mounting

# [Initial Raspberry Pi Setup:]

(1) [In Terminal: Show your Raspberry Pi version:]<br />
cat /etc/os-release

(2) [Update packages on your Raspberry Pi OS:]<br />
sudo apt-get update

(3) [Check Python Version:]<br />
python --version

(4) [Create / Move to a local directory:]<br />
cd Projects/<br />
mkdir Chu-Object-Detection-Fall-2021<br />
cd Chu-Object-Detection-Fall-2021<br />

(5) [Install virtualenv and upgrade pip:]<br />
python -m pip install --upgrade pip<br />
python -m pip install virtual env

(6) [Create a Python virtual enviroment for TFLite samples:]<br />
python -m venv ~/tflite


# [Initialize Virtual Enviroment + Run Object Recognition Script:]<br />
(1) [Activate Virtual Enviroment; Run this command when a new Terminal is open:]<br />
source ~/tflite/bin/activate

(2) [Change to working Directory:]<br />
pwd<br />
cd 'working directory with the the files'

(3) [Download Repo:]<br />
git clone https://github.com/schu-lab/TensorFlow-Object-Detection.git

(5a) [Run Object Detection Script (without model):]<br />
python Chu-Object-Detection-Fall-2021.py

(5b) [Run Object Detection Script (with model):]<br />
python Chu-Object-Detection-Fall-2021.py

** NOTE: Use 'Gun-Model-Eff1_SC.tflite' or 'Gun-Model-Eff1_SC.tflite' ** <br />
[EfficientDef-Lite0:] python Chu-Object-Detection-Fall-2021.py --model Gun-Model-Eff0_SC.tflite<br />
[EfficientDef-Lite1:] python Chu-Object-Detection-Fall-2021.py --model Gun-Model-Eff1_SC.tflite<br />

# Demo:
See Video File: https://github.com/schu-lab/Tensorflow-Object-Detection/raw/main/Object-Recognition-Demo.mp4

# [Train a Custom Object Detection Model using TensorFlow Lite Model Maker]<br />
NOTE: From TensorFlow Website: https://colab.research.google.com/github/khanhlvg/tflite_raspberry_pi/blob/main/object_detection/Train_custom_model_tutorial.ipynb

(2) [Preparation - Install packages]:<br />
pip install -q tflite-model-maker<br />
pip install -q tflite-support

(3) [Prepare Dataset by downloading images and annotating using Pascal VOC format (.xml)]:<br />
NOTE: Use labelImg or equivilent https://github.com/tzutalin/labelImg<br />

(4) [Select model architecture]: EfficientDet-Lite'0'<br />
NOTE: Dependency on Speed to Precision '0' to '4'

(5) [Train the TensorFlow model with Training Data]:<br />
NOTE: Typically 80% Training Model + 20% Test Model

(6) [Test the TensorFlow model with Test Data]:<br />
NOTE: Note the Average Precision (AP) based on the model architecture

(7) [Export the TensorFlow Lite model:]<br />
model.export(export_dir='.', tflite_filename='FILE_NAME.tflite')
NOTE: FILE_NAME is name of the file

(8) [Evaluate TensorFlow Lite Model]
