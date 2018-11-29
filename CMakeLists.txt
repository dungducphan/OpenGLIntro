cmake_minimum_required(VERSION 3.12)
project(OpenGLIntro)

# C++ Standard to use
set(CMAKE_CXX_STANDARD 14)

# Using PkgConfig
find_package(PkgConfig REQUIRED)

find_library(OPENGL_LIBRARY OPENGL)

# Set-up GLFW
pkg_search_module(GLFW REQUIRED glfw3)
include_directories(${GLFW_INCLUDE_DIRS})
link_directories(${GLFW_LIBRARY_DIRS})

# Set-up GLEW
pkg_search_module(GLEW REQUIRED glew)
include_directories(${GLEW_INCLUDE_DIRS})
link_directories(${GLEW_LIBRARY_DIRS})

# Build
add_executable(OpenGLIntro main.cpp)
target_link_libraries(OpenGLIntro ${GLFW_LIBRARIES} ${GLEW_LIBRARIES}  ${OPENGL_LIBRARY})