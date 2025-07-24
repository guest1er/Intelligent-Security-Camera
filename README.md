# Intelligent Security Camera

Description:

The Intelligent Security Camera can detect vehicles and deliveries powerd by a Jetson Nano with AI. vehciles like cars, truck, buses, and motorcycles. deliveries such as UPS, amazon, FedEx, and USPS. 

<img width="1440" height="810" alt="image" src="https://github.com/user-attachments/assets/7a08cd8b-864b-42b4-a132-96fbe265581a" />


## The Algorithm

The AI takes the input image / video and detects what it is in the view of the camera. The code will not run on a the newest version of the Jetson so you need to make sure it is on 1.26 in order for it to work.


## This is the link to the Dataset that i used for the vehicle detection: 

https://www.kaggle.com/datasets/kaggleashwin/vehicle-type-recognition?resource=download

## Running this project

pip install ultralytics (installs ultralytics)

yolo task=classify mode=train model=yolov8n-cls.pt data=/home/nvidia01/final_project/dataset epochs=60 imgsz=224 (trains the AI to detect what you want it to detect)

 yolo task=classify mode=val model=runs/classify/train2weights/best.pt data=/home/nvidia01/final_project/dataset/val ( (classifies the models)

yolo task=classify mode=predict model=/home/nvidia01/final_project/runs/classify/train2/weights/best.pt  source=/home/nvidia01/final_project/dataset/test (to test the model and give outputs)

yolo task=classify mode=predict model=/home/nvidia01/final_project/runs/classify/train2/weights/best.pt  source=0 (to run the camera)

yolo export model=/home/nvidia01/final_project/runs/classify/train2/weights/best.pt format=onnx (formats the models)


Video Link :
https://youtu.be/caAnpUTi_zw
