cmake_minimum_required(VERSION 3.16)

project(ImGuizmoTest)

add_definitions(-DSTB_IMAGE_IMPLEMENTATION)
find_path(STB_INCLUDE_DIRS "stb.h")

find_package(imgui CONFIG REQUIRED)
find_package(imguizmo CONFIG REQUIRED)

add_subdirectory(src)