cmake_minimum_required(VERSION 3.0)
project(Engine)

set(CMAKE_CXX_STANDARD 14)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

add_executable(Engine main.cpp)

cmake_policy(SET CMP0074 NEW)

find_package(GLFW3 3.3 REQUIRED)
target_link_libraries(Engine ${GLFW3_LIBRARY})
include_directories(${GLFW3_INCLUDE_DIR})

find_package(OpenGL REQUIRED)
target_link_libraries(Engine OpenGL::GL)
