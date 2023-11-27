cmake_minimum_required(VERSION 3.26)
project(CppImGuiPlayground)

set(CMAKE_CXX_STANDARD 17)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/imgui-master/backends/)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/imgui-master/)

find_package(glfw3 CONFIG REQUIRED)
find_package(OpenGL REQUIRED)


add_executable(CppImGuiPlayground main.cpp
        imgui-master/backends/imgui_impl_glfw.cpp
        imgui-master/backends/imgui_impl_opengl3.cpp
        imgui-master/imgui.cpp
        imgui-master/imgui_draw.cpp
        imgui-master/imgui_widgets.cpp
        imgui-master/imgui_tables.cpp)


target_link_libraries(CppImGuiPlayground PRIVATE glfw)
target_link_libraries(CppImGuiPlayground PRIVATE opengl32)