add_executable(Example)

target_sources(Example PRIVATE main.cpp)

target_compile_options(Example PRIVATE "/std:c++17")

target_include_directories(Example PRIVATE
    ${STB_INCLUDE_DIRS}
)

target_link_libraries(Example PRIVATE
    imgui::imgui
    imguizmo::imguizmo
)