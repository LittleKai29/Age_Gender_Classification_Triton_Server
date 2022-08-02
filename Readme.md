# How to run
```
Download model_repository 
For example pictures, download Cropfile folder
Run server
docker run --gpus=1 --rm -p 8000:8000 -v C://Users/Admin/Desktop/age_gender_googlenet/model_repository:/models nvcr.io/nvidia/tritonserver:22.06-py3 tritonserver --model-repository=/models
Running a model with example picture:
python age_googlenet.py -m age C:\Users\Admin\Downloads\Pictures\Face\Cropface\286276259_1043767066502793_8225607975713402140_n.jpg
```
Source:https://github.com/onnx/models/tree/main/vision/body_analysis/age_gender

Note:

  In the source, the models focus on classifying age and gender but skip the face detector step. So if you want a good result, please crop the face on image or use the face_detector model to preprocess.
  
  The age classification provides labels of 8 output classes, each of them is a value range of age includes : ['(0-2)', '(4-6)', '(8-12)', '(15-20)', '(25-32)', '(38-43)', '(48-53)', '(60-100)']
  
  The gender classification provides labels of 2 output classes, each of them represents for ['Male', 'Female'] classes
 
