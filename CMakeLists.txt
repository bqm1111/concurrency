cmake_minimum_required(VERSION 3.5)
project(concurrency)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3 -Wall -pthread")
set(CMAKE_CXX_STANDARD 17)
find_package(PkgConfig REQUIRED)

file(GLOB SOURCES ${PROJECT_SOURCE_DIR}/*.cpp)

add_executable(${PROJECT_NAME} ${SOURCES})

##----------------- OpenCV ---------------------------
find_package(OpenCV REQUIRED COMPONENTS core imgproc highgui videoio imgcodecs)
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})
