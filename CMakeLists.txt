cmake_minimum_required(VERSION 3.20)
project(imgui)

add_compile_definitions(IMGUI_IMPL_OPENGL_LOADER_CUSTOM) # Indicate to IMGUI that it doesn't need to find its own OPENGL3 loader
add_compile_definitions(IMGUI_IMPL_OPENGL_ES3)

include_directories(${PROJECT_SOURCE_DIR} backends/)

file(GLOB SOURCE_FILES ${PROJECT_SOURCE_DIR}/*.h ${PROJECT_SOURCE_DIR}/*.cpp)

add_library(imgui ${SOURCE_FILES}
                  ${PROJECT_SOURCE_DIR}/backends/imgui_impl_opengl3.h
                  ${PROJECT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp
                  ${PROJECT_SOURCE_DIR}/backends/imgui_impl_glfw.h
                  ${PROJECT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp)
