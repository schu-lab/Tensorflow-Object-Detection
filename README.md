# TensorFlow-Object-Detection
TensorFlow-Object-Detection using Python3, TensorFlow, OpenCV, and dataset (.jpg and .xml [Pascal VOC format])

Project to utilize TensorFlow to detect objects. 

References: 
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


# [Initial Raspberry Pi Setup:]

(1) [In Terminal: Show your Raspberry Pi version:]
cat /etc/os-release

(2) [Update packages on your Raspberry Pi OS:]
sudo apt-get update

(3) [Check Python Version:]
python --version

(4) [Create / Move to a local directory:]
cd Projects/
mkdir Chu-Object-Detection-Fall-2021
cd Chu-Object-Detection-Fall-2021

(5) [Install virtualenv and upgrade pip:]
python -m pip install --upgrade pip
python -m pip install virtual env

(6) [Create a Python virtual enviroment for TFLite samples:]
python -m venv ~/tflite


# [Initialize Virtual Enviroment + Run Object Recognition Script:]
(1) [Activate Virtual Enviroment; Run this command when a new Terminal is open:]
source ~/tflite/bin/activate

(2) [Change to working Directory:]
pwd
cd 'working directory with the the files'

(3) [Download Repo:]
git clone https://github.com/schu-lab/TensorFlow-Object-Detection.git

(5a) [Run Object Detection Script (without model):]
python Chu-Object-Detection-Fall-2021.py

(5b) [Run Object Detection Script (with model):]
python Chu-Object-Detection-Fall-2021.py --model 'FILE_NAME.tflite'
** NOTE: Use android.tflite file for FILE_NAME **
