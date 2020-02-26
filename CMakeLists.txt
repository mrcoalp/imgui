cmake_minimum_required(VERSION 3.0.0)
project(imgui VERSION 0.1.0)

include(CTest)
enable_testing()

add_library(imgui SHARED imgui.cpp)

target_include_directories(imgui INTERFACE
    $<BUILD_INTERFACE:${root}>
    $<INSTALL_INTERFACE:include>)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
