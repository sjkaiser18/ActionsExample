set (file01 "input01.txt")
set (file02 "input02.txt")
set (file03 "")
set (file04 "")
set (file05 "")

cmake_minimum_required(VERSION 3.12)
project(ActionsExample)

set(EXE_NAME sampleActionsOutput)

# Copy data files to build dir
foreach(file IN LISTS file01 file02 file03 file04 file05)
    configure_file(${file} ${file} COPYONLY)
endforeach()

set(CMAKE_CXX_STANDARD 17)
add_executable(${EXE_NAME} main.cpp GlobalFunctions.cpp)

