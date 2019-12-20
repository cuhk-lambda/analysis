project(Analysis)

cmake_minimum_required(VERSION 3.12)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-fPIC ${CMAKE_CXX_FLAGS} -lpthread -ldl -O3")
add_library(simdjson STATIC simdjson/singleheader/simdjson.cpp simdjson/singleheader/simdjson.h)
include_directories(simdjson/singleheader src)
add_executable(analyzer src/main.cpp)
target_link_libraries(analyzer simdjson)
