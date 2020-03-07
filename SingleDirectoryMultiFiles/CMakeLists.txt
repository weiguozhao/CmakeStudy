# 指定运行此配置文件所需的 CMake 的最低版本
cmake_minimum_required(VERSION 3.15)

# 该命令表示项目的名称
project(SingleDirectoryMultiFiles)

# 设置CXX的版本
set(CMAKE_CXX_STANDARD 14)

# 将main.cpp MathFunctions.cpp编译成一个名称为 SingleDirectoryMultiFiles 的可执行文件
# add_executable(SingleDirectoryMultiFiles main.cpp MathFunctions.cpp)

#### 下面的两条命令等价于上面注释的一条命令 ###

# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)
# 指定生成目标
add_executable(SingleDirectoryMultiFiles ${DIR_SRCS})