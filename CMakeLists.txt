cmake_minimum_required(VERSION 2.8)
project(Inc)

set(CMAKE_CXX_CFLAGS "-g -O0")


set(REALSEE_DIR /realsee)
set(OPENNI2_INCLUDE ${PROJECT_SOURCE_DIR}/thirdparty/OpenNI-Linux-ARM64-2.2/Include)
set(OPENNI2_LIB ${PROJECT_SOURCE_DIR}/thirdparty/OpenNI-Linux-ARM64-2.2/Redist)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")
LINK_DIRECTORIES(/realsee/lib)

add_definitions(-std=c++11)


add_executable(UVCTest
    ${PROJECT_SOURCE_DIR}/src/main.cpp
    )

# head file path
include_directories(
    ${OPENNI2_INCLUDE}
    ${REALSEE_DIR}/include
    )

target_link_libraries(UVCTest

    ${OPENNI2_LIB}/libOpenNI2.so
    ${REALSEE_DIR}/lib/libopencv_calib3d.so 
    ${REALSEE_DIR}/lib/libopencv_core.so 
    ${REALSEE_DIR}/lib/libopencv_features2d.so 
    ${REALSEE_DIR}/lib/libopencv_flann.so
    ${REALSEE_DIR}/lib/libopencv_highgui.so 
    ${REALSEE_DIR}/lib/libopencv_imgcodecs.so 
    ${REALSEE_DIR}/lib/libopencv_imgproc.so
    ${REALSEE_DIR}/lib/libopencv_ml.so
    ${REALSEE_DIR}/lib/libopencv_objdetect.so
    ${REALSEE_DIR}/lib/libopencv_photo.so
    ${REALSEE_DIR}/lib/libopencv_shape.so
    ${REALSEE_DIR}/lib/libopencv_stitching.so
    ${REALSEE_DIR}/lib/libopencv_superres.so
    ${REALSEE_DIR}/lib/libopencv_ts.a
    ${REALSEE_DIR}/lib/libopencv_video.so
    ${REALSEE_DIR}/lib/libopencv_videoio.so
    ${REALSEE_DIR}/lib/libopencv_videostab.so

    )
