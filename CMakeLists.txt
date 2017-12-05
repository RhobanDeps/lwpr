cmake_minimum_required(VERSION 2.8)
project(lwpr)

find_package(catkin REQUIRED COMPONENTS
  eigen
  )

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES lwpr
  CATKIN_DEPENDS eigen
)


#Include sources directory
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

#Sources files
set(SOURCES_FILES
    src/lwpr_aux.c  
    src/lwpr_binio.c  
    src/lwpr.c  
    src/lwpr_math.c  
    #src/lwpr_matlab.c  
    src/lwpr_mem.c  
    src/lwpr_xml.c  
)

#Build Code as static library
add_library(lwpr SHARED ${SOURCES_FILES})

