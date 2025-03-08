cmake_minimum_required(VERSION 3.10)  # Ensure CMake version is at least 3.10
project(gl3 C)  # Define the project name and specify that it uses C

# Set OpenGL preference to use GLVND instead of legacy OpenGL
set(OpenGL_GL_PREFERENCE GLVND)  # Prefer modern GLVND over legacy OpenGL

# Find required packages
find_package(OpenGL REQUIRED)  # Locate the OpenGL library
find_package(X11 REQUIRED)  # Locate the X11 library (for windowing support on Linux)

# Enforce C99 standard
set(CMAKE_C_STANDARD 99)  # Set the C standard to C99
set(CMAKE_C_STANDARD_REQUIRED ON)  # Ensure the C standard is strictly enforced

# Add the executable
add_executable(gl3 gl3.c)  # Create an executable named 'gl3' from 'gl3.cxx'

# Link the necessary libraries
target_link_libraries(gl3 PRIVATE OpenGL::GL X11)  # Link OpenGL and X11 to the executable

