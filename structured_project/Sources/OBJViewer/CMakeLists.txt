cmake_minimum_required (VERSION 3.22)
project (OBJViewer)

set(INCLUDE_DIR ./)
include_directories(${INCLUDE_DIR})
include_directories (.)

include_directories(${GLEW_INCLUDE_DIRS})
link_libraries(${GLEW_LIBRARIES})

include_directories(${SDL2_INCLUDE_DIR})
link_libraries(${SDL2_LIBRARY})
link_libraries(${SDL2main_LIBRARY})

include_directories(${SDL2_IMG_INCLUDE_DIR})
link_libraries(${SDL2_IMG_LIBRARY})

find_package(OpenGL REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS})
find_library(OPENGL32 opengl32.lib)
link_libraries(${OPENGL_LIBRARIES})

add_executable(OBJViewer OBJviewer.cpp
./ViewerApp.cpp
./ViewerObjectManager.cpp
)

target_link_libraries (OBJViewer Fregat)

# Creates a folder "executables" and adds target 
# project (app.vcproj) under it
set_property(TARGET OBJViewer PROPERTY FOLDER "executables")

# Properties->General->Output Directory
set_target_properties(OBJViewer PROPERTIES
                      RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin)
					  
install (TARGETS OBJViewer
         RUNTIME DESTINATION ${PROJECT_SOURCE_DIR}/_install)
		 

include(cmake/shaders_n_runtimelibs.cmake)
		
		