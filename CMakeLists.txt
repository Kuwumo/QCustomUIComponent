cmake_minimum_required(VERSION 3.22)

project(QCustomUIComponent VERSION 0.0.0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#设置qt5的环境变量
set(QT5_DIR "C:\\Qt\\5.15.2\\msvc2019_64")


add_subdirectory(src)
add_subdirectory(doc)
add_subdirectory(example)



