cmake_minimum_required(VERSION 3.10)
project(shaderArt VERSION 1.0)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find the packages
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)

# Include the GLFW headers and link the GLFW library
# Assuming GLFW is already configured elsewhere or is manually set up in this CMakeLists.txt
include_directories(${PROJECT_SOURCE_DIR}/glfw-3.4.bin.MACOS/include)
link_directories(${PROJECT_SOURCE_DIR}/glfw-3.4.bin.MACOS/lib-universal)

# Add source files
add_executable(shaderArt main.cpp)

# Link libraries to your target executable using target-based commands
target_link_libraries(shaderArt OpenGL::GL GLEW::GLEW glfw3 "-framework Cocoa" "-framework IOKit" "-framework CoreVideo")
