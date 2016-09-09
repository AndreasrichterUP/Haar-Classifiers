# Haar-Classifiers
This is a Haar-classifier to find foraminifera objects in microscope images.

It was build in about the same way as this one: 

http://coding-robin.de/2013/07/22/train-your-own-opencv-haar-classifier.html  
on a Linux Ubuntu, OpenCV 2.13

The one tricky thing was this part:

  cp src/mergevec.cpp ~/opencv/apps/haartraining
  cd ~/opencv/apps/haartraining
  g++ `pkg-config --libs --cflags opencv` -I. -o mergevec mergevec.cpp\
    cvboost.cpp cvcommon.cpp cvsamples.cpp cvhaarclassifier.cpp\
    cvhaartraining.cpp\
    -lopencv_core -lopencv_calib3d -lopencv_imgproc -lopencv_highgui -lopencv_objdetect

which had to be replace by :
  
  cp src/mergevec.cpp ~/opencv/apps/haartraining
  cd ~/opencv/apps/haartraining
  g++ `pkg-config --libs --cflags opencv` -I. -o mergevec mergevec.cpp\
    cvboost.cpp cvcommon.cpp cvsamples.cpp cvhaarclassifier.cpp\
    cvhaartraining.cpp\ cvsamplesoutput.cpp\
    -lopencv_core -lopencv_calib3d -lopencv_imgproc -lopencv_highgui -lopencv_objdetect
  
