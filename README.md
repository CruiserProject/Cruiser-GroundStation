# Cruiser-GroundStation
## Introduction
Ground station algorithms for Cruiser project which is used to detect whether there is any abnormal behavior you have defined occurs  in the video surveillance. It's going to alert when it happens.
## Collaborators
- [@ShoupingShan](https://github.com/ShoupingShan)
- [@finaldong](https://github.com/finaldong)
## Functions
- Object detection and classification
- Behavior detection
## Platform
- [Ubuntu 14.04](http://www.ubuntu.com/)
- [OpenCV 2.4.10](http://opencv.org/)
- [CUDA 8.0](http://www.nvidia.cn/object/cudazone-cn.html)
- [Darknet YOLO CNN](https://pjreddie.com/darknet)
## Demo
![fight](result/fight.jpeg)
## How to run

 ```
   $: git clone git@github.com:ShoupingShan/Abnormal-behavior-Detection.git
   $: cd Abnormal-behavior-Detection
   $: make
   $: wget https://pjreddie.com/media/files/yolo.weights
   $: ./darknet detector demo cfg/coco.data cfg/yolo.cfg yolo.weights -c 0
 ```

 ## Notes
 > **Makefile**
 > *This is what I use, uncomment if you know your arch and want to specify*

 > ARCH=  -gencode arch=compute_50,code=compute_50

 >**demo.c**

 >line 147 and line 154

 >Make sure you have replaced your own path!

 ## How to train
  >**First**, suppose you have collected your training video files such as `"samples.avi"`.

  >**Please** open and run `Video_cut/main.cpp`  then you can get many subfiles and each of them is 1 second. Delete some wrong files if exist(sometimes happens).

  >**Mark** sure these subfiles obeying this principle: rename the filename as `"f****.avi"`(starts with 'f') if it is abnormal. Otherwise, you needn't rename it.

  >**Return** to the Terminal:`ls > ../dir.txt`(get file path)  

  >**Make** a copy of yolo program, and `replace src/` by `train/src`,you can get same number of subfiles but ended with '`.dat`'.

  >**Return** to the Terminal:ls > ../dir.txt(get file path)

  >**Open** `train/SVM`, train this model automatically.

  >**Copy** `alpha.txt` and `out.txt` to yolo files, and amend `demo.c`.

## Contact Us
**Email**: shp395210@outlook.com
