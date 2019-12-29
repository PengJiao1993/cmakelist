cmake_minimum_required(VERSION 3.15)
project(Coastline)

find_package(OpenCV REQUIRED)
message(STATUS "OpenCV library status:")
message(STATUS "    version: ${OpenCV_VERSION}")
message(STATUS "    libraries: ${OpenCV_LIBS}")
message(STATUS "    include path: ${OpenCV_INCLUDE_DIRS}")

find_package(GDAL REQUIRED)
message(STATUS "GDAL library status:")
message(STATUS "    version: ${GDAL_VERSION}")
message(STATUS "    libraries: ${GDAL_LIBRARY}")
message(STATUS "    include path: ${GDAL_INCLUDE_DIRS}")

set(CMAKE_CXX_STANDARD 11)

include_directories(${GDAL_INCLUDE_DIRS} ${OpenCV_INCLUDE_DIRS})

add_executable(Coastline main.cpp)

target_link_libraries(Coastline ${OpenCV_LIBS} ${GDAL_LIBRARY})