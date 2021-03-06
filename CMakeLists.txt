cmake_minimum_required(VERSION 3.0.0)
project(VolumetricRenderer)
set(PROJECT_BRIEF "VolumetricRenderer")

set(CMAKE_AUTOMOC ON)

set(CMAKE_BUILD_TYPE RELEASE)
set(GCC_COMPILE_FLAGS "-std=c++11 -Wall -O3 -g -static")
set(GCC_LINK_FLAGS "")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GCC_COMPILE_FLAGS}")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${GCC_LINK_FLAGS}")


#qt
find_package(Qt5 COMPONENTS Core Widgets Gui OpenGL)
include_directories(${Qt5Widgets_INCLUDE_DIRS})

#glm
set(GLM_INC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/ext/glm CACHE PATH "Path to GLM")
include_directories(${GLM_INC_DIR})

#DCMTK
set(DCMTK_ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/ext/dcmtk/build/install CACHE PATH "Path to DCMTK")
set(DCMTK_INC_DIR ${DCMTK_ROOT_DIR}/include)
set(DCMTK_LIB_DIR ${DCMTK_ROOT_DIR}/lib)
set(DCMTK_BIN_DIR ${DCMTK_ROOT_DIR}/bin)
include_directories(${DCMTK_INC_DIR})
link_directories(${DCMTK_LIB_DIR})

#libtiff
set(LIBTIFF_ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR}/ext/libtiff/build/install CACHE PATH "Path to libtiff")
set(LIBTIFF_INC_DIR ${LIBTIFF_ROOT_DIR}/include)
set(LIBTIFF_LIB_DIR ${LIBTIFF_ROOT_DIR}/lib)
set(LIBTIFF_BIN_DIR ${LIBTIFF_ROOT_DIR}/bin)
include_directories(${LIBTIFF_INC_DIR})
link_directories(${LIBTIFF_LIB_DIR})



include_directories(src)
add_subdirectory(src)
