
CC = gcc

all: uvctest

CFLAGS=-I/realsee/include -I/realsee/include/opencv -I../thirdparty/OpenNI-Linux-ARM64-2.2/Include
LDFLAGS=-L/realsee/lib -lopencv_shape -lopencv_stitching -lopencv_objdetect -lopencv_superres -lopencv_videostab -lopencv_calib3d -lopencv_features2d -lopencv_highgui -lopencv_videoio -lopencv_imgcodecs -lopencv_video -lopencv_photo -lopencv_ml -lopencv_imgproc -lopencv_flann -lopencv_core   -L../thirdparty/OpenNI-Linux-ARM64-2.2/Redist -lOpenNI2




uvctest: main.o
	$(CC) $(LDFALGS) -o $@ main.o

main.o: main.cpp
	$(CC) main.cpp $(CFLAGS) -c 



clean:
	rm -f *.o uvctest
