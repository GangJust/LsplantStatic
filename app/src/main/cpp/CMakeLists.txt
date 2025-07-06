cmake_minimum_required(VERSION 3.28)

project(LsplantStatic CXX)

macro(SET_OPTION option value)
    set(${option} ${value} CACHE INTERNAL "" FORCE)
endmacro()

add_subdirectory(../../../../LSPlant/lsplant/src/main/jni lsplant_static)

add_library(${CMAKE_PROJECT_NAME} SHARED
        native-lib.cpp)

target_link_libraries(${CMAKE_PROJECT_NAME}
        android
        lsplant_static
        log)