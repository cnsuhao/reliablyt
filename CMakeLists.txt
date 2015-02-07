PROJECT(reliablyt)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8) 

ADD_DEFINITIONS(-D_CRT_SECURE_NO_WARNINGS)
ADD_DEFINITIONS(-D_WINSOCK_DEPRECATED_NO_WARNINGS)
ADD_DEFINITIONS(-D___mempool___)

set(BOOST_INCLUDE_PATH ${PROJECT_SOURCE_DIR}//third_party//boost CACHE PATH "BOOST include path")
INCLUDE_DIRECTORIES(${BOOST_INCLUDE_PATH})

set(BOOST_LIBS_PATH ${PROJECT_SOURCE_DIR}//third_party//boost//libs CACHE PATH "BOOST include path")
link_directories(${BOOST_LIBS_PATH})

set(reliablyt_include_path ${PROJECT_SOURCE_DIR} CACHE PATH "reliablyt include path")
INCLUDE_DIRECTORIES(${reliablyt_include_path})
MESSAGE(STATUS "This is include dir " ${reliablyt_include_path}) 

set(reliablyt_lib_path ${PROJECT_BINARY_DIR}/bin/Debug CACHE PATH "reliablyt lib path")
link_directories(${reliablyt_lib_path})
MESSAGE(STATUS "This is lib dir " ${reliablyt_lib_path}) 

set(reliablyt_bin_path ${PROJECT_BINARY_DIR}/bin CACHE PATH "reliablyt bin path")

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

ADD_SUBDIRECTORY(reliablyt ${reliablyt_bin_path}/reliablyt)
ADD_SUBDIRECTORY(test ${reliablyt_bin_path}/test)