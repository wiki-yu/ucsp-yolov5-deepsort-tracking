# Yolov5 + deepSORT for object tracking


## Summary of the process
The YOLO detector gets bbox → generates detections→ Kalman filter prediction → Use theHungarian algorithm to match the predicted trackswith the detections in the current frame(cascade matching and IOU matching) → Kalman filterupdate


## Getting Started

###  1. Setup Environment

#### 1.1 Create Virtual Environment

Create Virtual (Windows) Environment:

```shell script
python -m venv env
.\env\Scripts\activate
```

Create Virtual (Linux/Mac) Environment:

```shell script
python -m venv env
source env/bin/activate
```

#### 1.2 Install packages
```shell script
pip install -r requirements.txt
```

### 3. Training
- To save reviewe'time, skip training and directly go to the inference step (the trained detection model **best.pt** is in the main directory)
- there are 6 classes: person, bottle, computer, scanner, phone, tray
- if you want to train the detection model using YOLOv5, run the scripts as follows:

```shell script
# train YOLOv5s on the iAI dataset for 50 epochs
cd yolov5
pip install -r requirements.txt
python train.py --img 640 --batch 16 --epochs 50 --data pharmacy.yaml --weights yolov5s.pt
```

### 4. Inference
The YOLOv5 model trained using iAI datasets can be downloaded here:
[\[Teams Shared Data\]](https://teams.microsoft.com/_#/files/IAI-AI?threadId=19%3A2887ad0aaac040a1b7ad4681f0b867be%40thread.tacv2&ctx=channel&context=Pharmacy%2520videos&rootfolder=%252Fsites%252FFiiUSA-iAIGroup-IAI-AI%252FShared%2520Documents%252FIAI-AI%252FObject-Human%2520Detection%2520%2526%2520Tracking%252FPharmacy%2520videos),

- download a video from the link above
- put it under the main file folder and rename it as demo.mp4
- run the following script
```shell script
# get the tracking result
python track.py
```

### Evaluation
TODO

