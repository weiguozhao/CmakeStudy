# cmake最低版本
cmake_minimum_required(VERSION 3.15)

# 项目名称
project(CustomCompilationOptions)

# CXX版本
set(CMAKE_CXX_STANDARD 14)

# 添加了一个 USE_MYMATH 选项，并且默认值为 ON
# 是否使用自己的 MathFunctions 库，这个定义要放在config.h.in的前面
option(USE_MYMATH "Use provided math implementation" ON)

# 加入一个配置头文件，用于处理 CMake 对源码的设置
configure_file(
        # configure_file 命令用于加入一个配置头文件 config.h
        # 这个文件由 CMake 从 config.h.in 生成，
        # 通过这样的机制，将可以通过预定义一些参数和变量来控制代码的生成
        "${PROJECT_SOURCE_DIR}/config.h.in"
        "${PROJECT_BINARY_DIR}/config.h"
)

# 是否加入 MathFunctions 库
if (USE_MYMATH)
    include_directories("${PROJECT_SOURCE_DIR}/math")
    add_subdirectory(math)
    set(EXTRA_LIBS ${EXTRA_LIBS} MathFunctions)
endif (USE_MYMATH)

# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

# 生成可执行文件
add_executable(CustomCompilationOptions ${DIR_SRCS})

# 指定文件链接顺序
target_link_libraries(CustomCompilationOptions ${EXTRA_LIBS})

