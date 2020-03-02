cmake_minimum_required(VERSION 3.0.0)
project(imgui VERSION 0.1.0)

include(CTest)
enable_testing()

add_library(imgui SHARED
        imgui.cpp
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_widgets.cpp)

target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_LIST_DIR})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
