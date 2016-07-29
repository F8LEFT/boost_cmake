cmake_minimum_required(VERSION 3.5)
project(Boost_CMAKE)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

aux_source_directory(boost/libs/filesystem/src FILESYSTEM_SRC)
aux_source_directory(boost/libs/system/src SYSTEM_SRC)

add_library(Boost_CMAKE ${FILESYSTEM_SRC} ${SYSTEM_SRC})
#generate library
add_library(Boost_filesystem ${FILESYSTEM_SRC})
add_library(Boost_system ${SYSTEM_SRC})
target_include_directories(Boost_CMAKE PUBLIC boost)
target_include_directories(Boost_filesystem PUBLIC boost)
target_include_directories(Boost_system PUBLIC boost)
