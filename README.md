# OpenCV_Installation
Installing and setting up Opencv 3.4 on Ubuntu for C++

First, you should install some libraries before installing opencv 

`sudo apt -y remove x264 libx264-dev`

`sudo apt -y install build-essential checkinstall cmake pkg-config yasm`

`sudo apt -y install git gfortran`

`sudo apt -y install libjpeg8-dev libpng-dev`

`sudo apt -y install software-properties-common`

`sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"`

`sudo apt -y update`

`sudo apt -y install libjasper1`

`sudo apt -y install libtiff-dev`

`sudo apt -y install libavcodec-dev libavformat-dev libswscale-dev libdc1394-22-dev`

`sudo apt -y install libxine2-dev libv4l-dev`

`cd /usr/include/linux`

`sudo ln -s -f ../libv4l1-videodev.h videodev.h`

`cd "$cwd"`

`sudo apt -y install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev`

`sudo apt -y install libgtk2.0-dev libtbb-dev qt5-default`

`sudo apt -y install libatlas-base-dev`

`sudo apt -y install libfaac-dev libmp3lame-dev libtheora-dev`

`sudo apt -y install libvorbis-dev libxvidcore-dev`

`sudo apt -y install libopencore-amrnb-dev libopencore-amrwb-dev`

`sudo apt -y install libavresample-dev`

`sudo apt -y install x264 v4l-utils`

Optional dependencies

`sudo apt -y install libprotobuf-dev protobuf-compiler`

`sudo apt -y install libgoogle-glog-dev libgflags-dev`

`sudo apt -y install libgphoto2-dev libeigen3-dev libhdf5-dev oxygen`

`sudo apt-get install ubuntu-restricted-extras`



1- Create a new file called opencv_installation 

`mkdir opencv_installation`

`cd opencv_installation`

2- clone the two folders opencv and opencv_contrib from GitHub repo

`git clone https://github.com/opencv/opencv.git`

`https://github.com/opencv/opencv_contrib.git`

3- Make a file named build inside opencv folder

`cd opencv`

`mkdir build`

`cd build`

4- Inside the build file run this cmake command (make sure that you have installed cmake before)

`cmake -D CMAKE_BUILD_TYPE=RELEASE \
          -D CMAKE_INSTALL_PREFIX=/usr/local \
          -D INSTALL_C_EXAMPLES=OFF \
          -D INSTALL_PYTHON_EXAMPLES=OFF \
          -D ENABLE_FAST_MATH=ON \
          -D BUILD_opencv_java=OFF \
          -D BUILD_ZLIB=ON \
          -D BUILD_TIFF=ON \
          -D WITH_GTK=ON \
          -D WITH_FFMPEG=ON \
          -D WITH_1394=ON \
          -D OPENCV_GENERATE_PKGCONFIG=ON \
          -D OPENCV_PC_FILE_NAME=opencv3.pc \
          -D OPENCV_ENABLE_NONFREE=ON \
          -D WITH_GSTREAMER=ON \
          -D WITH_V4L=ON \
          -D WITH_QT=ON \
          -D WITH_OPENGL=ON \
          -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
          -D BUILD_EXAMPLES=ON ..`


5- run the make file 

`make -j4`

(if you have 8 cores you can yous make -j8 it will be faster)


6-Final step 

`sudo make install`

to make sure if the opencv is instaled or not run the following command 

`pkg-config --modversion opencv3`

it will print the opencv version 
(if you installing opencv 4 "use pkg-config --modversion opencv4")
