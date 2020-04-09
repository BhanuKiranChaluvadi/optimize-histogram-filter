cmake_minimum_required(VERSION 3.10)

# set the project name and version
project(histogram_filter VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# specify Release/Debug build type
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

# set CXX flags
set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

# Create a sources variable with a link to all cpp files to compile
# file(GLOB SOURCES "*.cpp")

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    main.cpp
    normalize.cpp
    sense.cpp
    blur.cpp
    initialize_beliefs.cpp
    move.cpp 
    print.cpp 
    zeros.cpp
)

# add the executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/
target_include_directories(${PROJECT_NAME}
    PRIVATE 
        ${PROJECT_SOURCE_DIR}/headers
)
