# CMake 最低版本号要求
cmake_minimum_required(VERSION 3.15)

# 项目名称
project(MultiDirectoriesMultiFiles)

# CXX版本
set(CMAKE_CXX_STANDARD 14)

# 添加 math 子目录
add_subdirectory(math)

# 指定生成目标
add_executable(MultiDirectoriesMultiFiles main.cpp)

# 添加链接库
target_link_libraries(MultiDirectoriesMultiFiles MathFunctions)
