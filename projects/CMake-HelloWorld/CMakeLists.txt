# CMakeList.txt : CMake project for CMake-HelloWorld, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

project ("CMake-HelloWorld")

# Add source to this project's executable.
add_executable ("${PROJECT_NAME}" "src/CMake-HelloWorld.cpp" "inc/CMake-HelloWorld.h")

include_directories ("inc;")

if (EMSCRIPTEN)
	set (CMAKE_EXECUTABLE_SUFFIX ".html")
endif()

# Include sub-projects.
#add_subdirectory ("CMake-HelloWorld")

set (CMAKE_BINARY_DIR "${CMAKE_HOME_DIRECTORY}/bin/${CMAKE_BUILD_TYPE}/${PROJECT_NAME}/")
set (EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})