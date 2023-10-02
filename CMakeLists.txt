cmake_minimum_required(VERSION 3.26)
project(hello-c)

set(CMAKE_CXX_STANDARD 17)

# 设置 hello-cpp 项目构建目录的路径
set(HELLO_CPP_PATH D:/Workspace/LibraryWorkspace/C/hello-cpp)
set(HELLO_CPP_MODULE1_PATH ${HELLO_CPP_PATH}/module1)
#
add_executable(hello-c main.c)
#
#
## hello-cpp项目module1模块的头文件目录
target_include_directories(hello-c PRIVATE ${HELLO_CPP_MODULE1_PATH}/include)
#


## 如果 untitled 需要链接其他库，可以在这里添加链接命令(项目之间的以下使用绝对路径方式)
#target_link_libraries(hello-c PRIVATE HelloCppModule1)

## 链接到HelloCppModule1库
target_link_libraries(hello-c ${HELLO_CPP_MODULE1_PATH}/libHelloCppModule1.a)
#






