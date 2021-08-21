cmake_minimum_required(VERSION 3.0)
project(Engine)

set(CMAKE_CXX_STANDARD 14)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

file(GLOB SOURCES *.cpp src/*.cpp src/*.c)
add_executable(Engine ${SOURCES})

cmake_policy(SET CMP0074 NEW)

target_include_directories(Engine PRIVATE include)
target_include_directories(Engine PRIVATE src)

find_package(GLFW3 3.3 REQUIRED)
target_link_libraries(Engine ${GLFW3_LIBRARY})
include_directories(${GLFW3_INCLUDE_DIR})

find_package(OpenGL REQUIRED)
target_link_libraries(Engine OpenGL::GL)
