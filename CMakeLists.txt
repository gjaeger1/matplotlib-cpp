cmake_minimum_required(VERSION 3.0.0)
project(matplotlibcpp VERSION 0.1 LANGUAGES CXX)


set(MATPLOTLIB_CPP_DEPS "")
set(MATPLOTLIB_CPP_DEST_DIR "${CMAKE_INSTALL_PREFIX}")
set(MATPLOTLIB_CPP_VERSION ${PROJECT_VERSION})
set(MATPLOTLIB_CPP_CFLAGS)

string(REPLACE ";" " -l" MATPLOTLIB_CPP_DEPS_STR "${MATPLOTLIB_CPP_DEPS}")
string(REPLACE ";" " " MATPLOTLIB_CPP_CFLAGS_STR "${MATPLOTLIB_CPP_CFLAGS}")

CONFIGURE_FILE("matplotlibcpp.pc.in" "matplotlibcpp.pc" @ONLY)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/matplotlibcpp.pc DESTINATION share/pkgconfig)
install(FILES matplotlibcpp.h DESTINATION include/matplotlibcpp)

