cmake_minimum_required(VERSION 3.10)  # 指定 CMake 的最低版本要求

project(test)  # 设置项目名称

set(CMAKE_CXX_STANDARD 11)  # 指定 C++ 标准为 C++11（根据需要可以更改）

# set(CMAKE_OSX_ARCHITECTURES "x86_64")

# 添加可执行文件
add_executable(test main.cpp glad.c)  # 将 main.cpp 文件编译成可执行文件 main

# 指定 glfw 库的路径
set(GLFW_LIB_PATH "${CMAKE_SOURCE_DIR}/include/GLFW/lib/libglfw3.a")

# 链接 glfw 库
target_link_libraries(test ${GLFW_LIB_PATH} "-framework Cocoa -framework IOKit -framework CoreVideo -framework OpenGL")

# 查找并包含 GLFW 头文件（可选，如果你有 glfw 的头文件）
include_directories("${CMAKE_SOURCE_DIR}/include")
