cmake_minimum_required (VERSION 3.22)
project (OBJViewerSolution)

set(INCLUDE_DIR ./)
include_directories(${INCLUDE_DIR})

set_property(GLOBAL PROPERTY USE_FOLDERS ON)
message ("cxx Flags: " ${CMAKE_CXX_FLAGS})

include(cmake/3rd_party.cmake)

add_subdirectory(Tests)
add_subdirectory(Fregat)
add_subdirectory(OBJViewer)