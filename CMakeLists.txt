cmake_minimum_required(VERSION 3.22.2)

# set the project name and version
project(OpenGL_project VERSION 1.0.0 LANGUAGES CXX)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

configure_file(${CMAKE_SOURCE_DIR}/src/res/shaders/Basic.shader ${CMAKE_CURRENT_BINARY_DIR}/res/shaders/Basic.shader COPYONLY)

add_executable(openglexe ${CMAKE_SOURCE_DIR}/src/main.cpp)

# target_include_directories("${CMAKE_PROJECT_NAME}" PUBLIC "${PROJECT_BINARY_DIR}/include")
target_include_directories(openglexe PUBLIC ${CMAKE_SOURCE_DIR}/include)

add_library(glfw3 STATIC IMPORTED)
add_library(GLEW STATIC IMPORTED)
# Provide the full path to the library, so CMake knows where to find it.
set_target_properties(glfw3 PROPERTIES IMPORTED_LOCATION ${CMAKE_SOURCE_DIR}/libs/libglfw3.a)
set_target_properties(GLEW PROPERTIES IMPORTED_LOCATION ${CMAKE_SOURCE_DIR}/libs/libGLEW.a)

target_link_libraries(openglexe glfw3 OpenGL pthread dl X11 GLEW GLX)