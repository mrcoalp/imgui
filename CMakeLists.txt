cmake_minimum_required(VERSION 3.0.0)
project(imgui VERSION 0.1.0)

option(BUILD_SHARED_LIBS "Build shared libraries" ON)

include(CTest)
enable_testing()

if (BUILD_SHARED_LIBS)
    set(LIB_TYPE SHARED)
else ()
    set(LIB_TYPE STATIC)
endif ()

add_library(imgui ${LIB_TYPE}
        imgui.cpp
        imgui_demo.cpp
        imgui_draw.cpp
        imgui_widgets.cpp)

target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_LIST_DIR})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

install(TARGETS imgui DESTINATION lib)
install(FILES
        imconfig.h
        imgui_internal.h
        imgui.h
        imstb_rectpack.h
        imstb_textedit.h
        imstb_truetype.h
        DESTINATION include)
