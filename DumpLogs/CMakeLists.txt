cmake_minimum_required(VERSION 2.8)
SET(CMAKE_BUILD_TYPE Debug)

SET(CMAKE_VERBOSE_MAKEFILE TRUE)

FIND_PACKAGE(MPI REQUIRED)

INCLUDE_DIRECTORIES(${MPI_INCLUDE_PATH})

ADD_EXECUTABLE(dumpLogs
	main.cpp 
	dump_logs.cpp
  )

TARGET_LINK_LIBRARIES(dumpLogs
  ${MPI_LIBRARY}
  ${MPI_EXTRA_LIBRARY}
  )


SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")