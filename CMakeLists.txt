cmake_minimum_required(VERSION 3.5)

project(pirulo LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt5 COMPONENTS Widgets REQUIRED)

add_executable(pirulo
  main.cpp
  window.cpp
  window.h
  pirulo.qrc
)

target_link_libraries(pirulo PRIVATE Qt5::Widgets)
if (MINGW OR MSYS) 
  target_link_options(pirulo PRIVATE -mwindows)
endif()
