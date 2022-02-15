cmake_minimum_required(VERSION 3.5)

project(opengl_window LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(opengl_window main.cpp)

if(UNIX)
    target_link_libraries(opengl_window glfw GLEW GL)
endif(UNIX)

if(WIN32)
    add_definitions(-DGLEW_STATIC)
    target_link_libraries(opengl_window glfw3 GLEW opengl32)
endif(WIN32)
