# Yolo-implementation-using-Intel-Movidius-Neural-Compute-Stick-NCS-on-Raspberry-Pi

## Intel Movidius Neural Compute Stick (NCS) Setup

* Install NCSDK for the Movidius stick to work on Raspberry Pi.
  
  if it fails at :

	* If NCSDK fails to setup the Intel Movidius NCS download caffe from git if the installation fails
	* NCS also required ssd-caffe to run the model
		
                NOTE :
		* If any of the above mentioned or any other package suffers installation all the required file are available at movidius/*.
											 All the files were tested. 


## News

* Works on both Rpi and DSI ( Rpi Camera Module)
* YOLOv1 Tiny is working.

## Protobuf Model files

./prototxt/

## Download Pretrained Caffe Models to ./weights/

* YOLO_tiny: https://pjreddie.com/media/files/yolov2-tiny.weights

## Compilation

* Compile .prototxt and corresponding .caffemodel (with the same name) to get NCS graph file. For example: "mvNCCompile prototxt/yolo_tiny_deploy.prototxt -w weights/yolo_tiny_deploy.caffemodel -s 12"
* The compiled binary file "graph" has to be in main folder after this step.

## Single Image Script

* Run "yolo_image_predict.py" to process a single image. For example: "python3 function/yolo_image_predict.py images/dog.jpg" to get detections as below.

![](/images/yolo_dog.png)

## Camera Input Script

	
* Run "yolo_video.py" to process a videos from your camera. For example: "python3 function/yolo_video.py" to get camera detections as below.
* Modify script arguments if needed.
* Press "q" to exit app.

$ NOTE : To run with external USB camera interfaced with Raspberry Pi, comment line #164 on function/yolo_video.py
![](/images/camera.png)



