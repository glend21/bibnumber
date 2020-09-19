cmake_minimum_required(VERSION 2.8)
project( BibNumber )

find_package( OpenCV REQUIRED )

include_directories( ${OpenCV_INCLUDE_DIRS} )


add_library( bibnumber SHARED 
                batch.cpp
                facedetection.cpp
                log.cpp
                pipeline.cpp
                textdetection.cpp
                textrecognition.cpp )

install( TARGETS bibnumber DESTINATION $ENV{HOME}/lib64 )
install( FILES TextDetection.h batch.h DESTINATION $ENV{HOME}/include )
