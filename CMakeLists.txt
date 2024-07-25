cmake_minimum_required(VERSION 3.9.0)  
project(demo)                    

message(STATUS "begin include")
include("cmake/test_cmake.cmake")
include("cmake/test_cmake1.cmake" OPTIONAL) #OPTIONAL 可选，文件不存在不报错
include("cmake/test_cmake1.cmake" OPTIONAL  RESULT_VARIABLE ret) # RESULT_VARIABLE 返回值，是否引用成功
message(STATUS "RESULT_VARIABLE ret= ${ret}") #NOTFOUND
include("cmake/test_cmake.cmake" OPTIONAL  RESULT_VARIABLE ret)
message(STATUS "RESULT_VARIABLE ret= ${ret}") #导入文件的绝对路径
message(STATUS "end include")

add_executable(app main.c) 

