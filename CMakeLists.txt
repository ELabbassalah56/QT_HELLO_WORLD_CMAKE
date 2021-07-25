
cmake_minimum_required(VERSION 3.4)

project(helloworld VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

set(OE_QMAKE_PATH_EXTERNAL_HOST_BINS $ENV{OE_QMAKE_PATH_HOST_BINS})

find_package(Qt5 COMPONENTS Widgets REQUIRED)


set(QT_LIBRARIES Qt5::Widgets)
add_executable(helloworld
    mainwindow.ui
    mainwindow.cpp
    main.cpp
    resources.qrc
)

target_link_libraries(helloworld Qt5::Widgets)