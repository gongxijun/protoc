cmake_minimum_required(VERSION 3.8)
project(demo)
add_definitions(-std=c++11)
aux_source_directory(. DIR_LIB_SRCS)
set(LIBS  gflags glog zmq protobuf mxnet )

add_subdirectory(proto)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR} )

add_executable(demo ${DIR_LIB_SRCS} ${PROTO_HEADER})
target_link_libraries(demo ${LIBS} proto ${PROTOBUF_LIBRARY})