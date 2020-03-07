
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_LIB_SRCS 变量
aux_source_directory(. DIR_LIB_SRCS)

# 生成链接库
add_library(MathFunctions ${DIR_LIB_SRCS})

# 指定 MathFunctions 库的安装路径
# MathFunctions.a 安装到 /usr/local/lib 中
install(TARGETS MathFunctions DESTINATION lib)
# MathFunctions.h 安装到 /usr/local/include 中
install(FILES MathFunctions.h DESTINATION include)
