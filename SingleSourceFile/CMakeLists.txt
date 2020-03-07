# 指定运行此配置文件所需的 CMake 的最低版本
cmake_minimum_required(VERSION 3.15)

# 该命令表示项目的名称
project(SingleSourceFile)

# 执行项目的CXX版本
set(CMAKE_CXX_STANDARD 14)

# 将名为 main.cpp 的源文件编译成一个名称为 SingleSourceFile 的可执行文件
add_executable(SingleSourceFile main.cpp)