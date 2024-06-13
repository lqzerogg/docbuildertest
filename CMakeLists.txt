# CMake 最低版本要求
cmake_minimum_required(VERSION 3.10)

# 工程名称
project(docbuildertest)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 11)

# 设置构建类型为 Debug
set(CMAKE_BUILD_TYPE Debug)

# 添加调试信息和禁用优化的编译选项
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -O0")

# 把源文件添加到一个变量中
set(SOURCES
    main.cpp
)

# 指定库文件的路径
set(LIBRARY_PATH /opt/onlyoffice/documentbuilder)

# 添加可执行文件
add_executable(main ${SOURCES})

# 链接库文件
target_link_libraries(main
  ${LIBRARY_PATH}/libdoctrenderer.so
  ${LIBRARY_PATH}/libDocxRenderer.so
  ${LIBRARY_PATH}/libgraphics.so
  )

