cmake_minimum_required(VERSION 2.8)

project(git-tree-graph)

add_subdirectory(qgit2)

find_package(Qt4 4.8.3 REQUIRED QtCore QtGui)

set(git-tree-graph_sources main.cpp treegraphwindow.cpp)

set(git-tree-graph_headers treegraphwindow.h)

qt4_wrap_cpp(git-tree-graph_headers_moc ${git-tree-graph_headers_moc})

include(${QT_USE_FILE})
add_definitions(${QT_DEFINITIONS})

add_executable(git-tree-graph ${git-tree-graph_sources}
	${git-tree-graph_headers_moc})
target_link_libraries(git-tree-graph ${QT_LIBRARIES})
