cmake_minimum_required(VERSION 3.12)
project(Steamlein)

include_directories(include/Steamlein)

file(GLOB_RECURSE SOURCES *.cpp)

if (CMAKE_VERSION VERSION_LESS 3.15)
    add_library(${PROJECT_NAME} OBJECT ${SOURCES})
else()
    add_library(${PROJECT_NAME} ${SOURCES})
endif()
target_include_directories(${PROJECT_NAME} PUBLIC include)

target_link_libraries(${PROJECT_NAME} PUBLIC simplyfile)

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD_REQUIRED TRUE)
