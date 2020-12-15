# Real-time-Gun-Detection
Real-time Gun detection using darknet and OpenCV

Introduction-
With increase in number of installation of CCTV cameras around us, it is important to perform various ways to prevent anomalies or mishappenings. The most used object for crime is a gun, so here we 
have implemented a real-time gun detection project which will automatically detect a gun in CCTV footages and various authorities can be alerted about it.



Dataset preparation-
The dataset contains .jpg files of guns and each image is associated with a label file which has the information in this syntax: <object-class> <x_center> <y_center> <width> <height>
The data is annotated using LabelImg( https://github.com/tzutalin/labelImg#labelimg ) where you can manually open each image, draw the bounding box around the object(gun in our case) and automatically save the label file with data in the above syntax.

You can also download the prepared dataset from this site: http://www.mediafire.com/file/pvfircmboaelkxc/Gun_data_labeled.zip/file
The dataset contains 3000 images of guns with their corresponding label files. The dataset was split into train and validation sets.

Methodology-
The Darknet package is used to implement YOLO v-3 to train and get the weights on our gun dataset.. YOLO(You Only Look Once) is an extremely fast object detection algorithm mainly used for real time detection. It is faster than Faster RCNN and RCNN and is widely being used.
After training, the trained weights are extracted. OpenCV is used for input and video processing. YOLO v3 used the already trained weights to perform the detection task
on the input video given, and we get the output as a video with rectangle drawn around the gun(if found). 
