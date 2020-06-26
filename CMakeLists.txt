cmake_minimum_required(VERSION 3.0.0)
project(matplotlibcpp VERSION 0.1 LANGUAGES CXX)

find_package(Python3 COMPONENTS Development NumPy REQUIRED)
set(MATPLOTLIB_CPP_INCLUDE_DIRS ${Python3_INCLUDE_DIRS} ${Python3_NumPy_INCLUDE_DIRS})
set(MATPLOTLIB_CPP_DEPS Python3::Python Python3::NumPy)
set(MATPLOTLIB_CPP_DEST_DIR "${CMAKE_INSTALL_PREFIX}")
set(MATPLOTLIB_CPP_VERSION ${PROJECT_VERSION})
set(MATPLOTLIB_CPP_CFLAGS)

CONFIGURE_FILE("matplotlibcpp.pc.in" "matplotlibcpp.pc" @ONLY)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/matplotlibcpp.pc DESTINATION share/pkgconfig)
install(FILES matplotlibcpp.h DESTINATION include/matplotlibcpp)

