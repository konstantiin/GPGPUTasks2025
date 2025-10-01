cmake_minimum_required(VERSION 3.5)

set( CMAKE_CXX_COMPILER "D:/programs/msys64/clang64/bin/clang++.exe" )
set( CMAKE_C_COMPILER "D:/programs/msys64/clang64/bin/clang.exe" )
project(GPGPUTasks)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(libs)

# Компилируем исполняемый файл нашей программы
add_executable(enumDevices src/main.cpp)

# Мы линкуемся с библиотекой clew (см. папку libs/clew) - она содержит в себе OpenCL headers + позволяет в runtime слинковаться с OpenCL API функциями
target_link_libraries(enumDevices libclew)
