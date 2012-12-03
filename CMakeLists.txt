cmake_minimum_required(VERSION 2.8)

project(git-tree-graph)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/modules)

find_package(Git2 REQUIRED)
find_package(Qt4 4.8.3 REQUIRED QtCore QtGui)

set(git-tree-graph_sources main.cpp treegraphwindow.cpp)

set(git-tree-graph_headers treegraphwindow.h)

qt4_wrap_cpp(git-tree-graph_headers_moc ${git-tree-graph_headers_moc})

include_directories(${GIT2_INCLUDE_DIR})
include(${QT_USE_FILE})
add_definitions(${QT_DEFINITIONS})

add_executable(git-tree-graph ${git-tree-graph_sources}
	${git-tree-graph_headers_moc})
target_link_libraries(git-tree-graph ${QT_LIBRARIES})
