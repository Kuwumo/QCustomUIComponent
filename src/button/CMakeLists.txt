#这里有个问题，VS中不显示头文件和cpp文件分组，这个需要学习一下
file(GLOB SRCS "*.cpp *.h *.ui *.qrc *.hpp")

#添加源文件直接用下述命令即可，file指令为查询所有文件
#aux_source_directory(. SRCS)
#include_directories(./include)

#设置QT的自动moc，自动根据ui文件生成头文件，自动ui，自动生成资源文件
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

#查找qt对应的组件库
find_package(Qt5 COMPONENTS Core Gui Widgets REQUIRED)
include_directories(${Qt5Widgets_INCLUDE_DIRS})

#生成动态库
add_library(button SHARED ${SRCS})

# 链接Qt5库
target_link_libraries(button PRIVATE Qt5::Core Qt5::Gui Qt5::Widgets)
