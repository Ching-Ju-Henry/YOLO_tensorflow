# YOLO on Tensorflow
This YOLO code, I forked from https://github.com/gliese581gg/YOLO_tensorflow
</br> (1) I only use it for trsting without any changing
</br> (2) This code without training code, so if I want to train it, using https://github.com/hizhangp/yolo_tensorflow or see what &emsp; &emsp; 'Introduction' said.

### Introduction
This is tensorflow implementation of the YOLO:Real-Time Object Detection
It can only do predictions using pretrained YOLO_small & YOLO_tiny network for now.
(+ YOLO_face detector from https://github.com/quanhua92/darknet )
I extracted weight values from darknet's (.weight) files.
My code does not support training. Use darknet for training.
Original code(C implementation) & paper : http://pjreddie.com/darknet/yolo/

### Install
(1) Download code

(2) Download YOLO weight file from
</br> YOLO_small : https://drive.google.com/file/d/0B2JbaJSrWLpza08yS2FSUnV2dlE/view?usp=sharing
</br> YOLO_tiny  : https://drive.google.com/file/d/0B2JbaJSrWLpza0FtQlc3ejhMTTA/view?usp=sharing
</br> YOLO_face : https://drive.google.com/file/d/0B2JbaJSrWLpzMzR5eURGN2dMTk0/view?usp=sharing

(3) Put the 'YOLO_(version).ckpt' in the 'weight' folder of downloaded code

### Usage

(1) direct usage with default settings (display on console, show output image, no output file writing)

	python YOLO_(small or tiny)_tf.py -fromfile (input image filename)

(2) direct usage with custom settings

	python YOLO_(small or tiny)_tf.py argvs

	where argvs are

	-fromfile (input image filename) : input image file
	-disp_console (0 or 1) : whether display results on terminal or not
	-imshow (0 or 1) : whether display result image or not
	-tofile_img (output image filename) : output image file
	-tofile_txt (output txt filename) : output text file (contains class, x, y, w, h, probability)

(3) import on other scripts

	import YOLO_(small or tiny)_tf
	yolo = YOLO_(small or tiny)_tf.YOLO_TF()

	yolo.disp_console = (True or False, default = True)
	yolo.imshow = (True or False, default = True)
	yolo.tofile_img = (output image filename)
	yolo.tofile_txt = (output txt filename)
	yolo.filewrite_img = (True or False, default = False)
	yolo.filewrite_txt = (True of False, default = False)

	yolo.detect_from_file(filename)
	yolo.detect_from_cvmat(cvmat)

### Requirements
- Tensorflow
- Opencv2
