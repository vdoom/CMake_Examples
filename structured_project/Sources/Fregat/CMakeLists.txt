cmake_minimum_required (VERSION 3.22)
project (Fregat)

set(INCLUDE_DIR ./)
include_directories(${INCLUDE_DIR})
include_directories (.)

include_directories(${GLEW_INCLUDE_DIRS})
include_directories(${SDL2_INCLUDE_DIR})
include_directories(${SDL2_IMG_INCLUDE_DIR})

# SHARED
add_library(Fregat _API.h
./System/Assets/AssetsManagement/AssetBin.cpp
./System/Assets/AssetsManagement/AssetsManager.cpp
./System/Assets/Render/Components/RendererComponent.cpp
./System/Assets/Render/Material/SimpleMaterial.cpp
./System/Assets/Render/Mesh/ComplexGeometry3D.cpp
./System/Assets/Render/Mesh/Geometry3D.cpp
./System/Assets/Render/Mesh/MeshPlane.cpp
./System/Assets/Render/Mesh/MeshStatic.cpp
./System/Assets/Render/Shader/Shader.cpp
./System/Assets/Render/Texture/BitMap2D.cpp
./System/Assets/Render/Texture/Texture2D.cpp
./System/Static3DObjectFabriacator.cpp
./System/Core/ServiceLocator.cpp
./System/Core/Component.cpp
./System/Core/Entity.cpp
./System/Core/ObjectManager.cpp
./System/Core/Transform.cpp
./System/IO/FileFormats/OBJimporter.cpp
./System/Renderer/BaseRenderer.cpp
./System/Renderer/Camera.cpp
./System/Renderer/FPSCamera.cpp
./System/Renderer/OpenGL33Renderer.cpp
)

SOURCE_GROUP("Fregat\\MathLib" FILES 
./MathLib/AABB.h
./MathLib/EasingLib.h
./MathLib/Mat3.h 
./MathLib/Mat4.h
./MathLib/MathCommon.h
./MathLib/MatOperations.h
./MathLib/Rect.h
./MathLib/Vec2.h
./MathLib/Vec3.h
./MathLib/Vec4.h
)

SOURCE_GROUP("Fregat\\System\\Tools" FILES 
./System/Tools/UUID.h
./System/Tools/Delegat.h
./System/Tools/Logger.h
)

SOURCE_GROUP("Fregat\\System\\Renderer" FILES 
./System/Renderer/BaseRenderer.cpp
./System/Renderer/BaseRenderer.h
./System/Renderer/Camera.cpp
./System/Renderer/Camera.h
./System/Renderer/FPSCamera.cpp
./System/Renderer/FPSCamera.h
./System/Renderer/ICamera.h
./System/Renderer/OpenGL33Renderer.cpp
./System/Renderer/OpenGL33Renderer.h
)

SOURCE_GROUP("Fregat\\System\\IO\\Inputs" FILES 
./System/IO/Inputs/BaseInputController.h
./System/IO/Inputs/SDLInputController.h
)

SOURCE_GROUP("Fregat\\System\\IO\\FileFormats" FILES 
./System/IO/FileFormats/OBJimporter.cpp
./System/IO/FileFormats/OBJimporter.h
./System/IO/FileFormats/ParsersDataStructures.h
)

SOURCE_GROUP("Fregat\\System\\Core" FILES 
./System/Core/App.h
./System/Core/ServiceLocator.h
./System/Core/ServiceLocator.cpp
./System/Core/IService.h
./System/Core/IWindow.h
./System/Core/SDLWindow.h
./System/Core/Component.cpp
./System/Core/Component.h
./System/Core/Entity.cpp
./System/Core/Entity.h
./System/Core/ObjectManager.cpp
./System/Core/ObjectManager.h
./System/Core/Transform.cpp
./System/Core/Transform.h
)

SOURCE_GROUP("Fregat\\System" FILES 
./System/OverridedTypes.h
./System/Static3DObjectFabriacator.cpp
./System/Static3DObjectFabriacator.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\Render\\Texture" FILES 
./System/Assets/Render/Texture/BitMap2D.cpp
./System/Assets/Render/Texture/BitMap2D.h
./System/Assets/Render/Texture/Texture2D.cpp
./System/Assets/Render/Texture/Texture2D.h
./System/Assets/Render/Texture/TextureBase.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\Render\\Shader" FILES 
./System/Assets/Render/Shader/Shader.cpp
./System/Assets/Render/Shader/Shader.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\Render\\Mesh" FILES 
./System/Assets/Render/Mesh/ComplexGeometry3D.cpp
./System/Assets/Render/Mesh/ComplexGeometry3D.h
./System/Assets/Render/Mesh/Geometry3D.cpp
./System/Assets/Render/Mesh/Geometry3D.h
./System/Assets/Render/Mesh/MeshBase.h
./System/Assets/Render/Mesh/MeshPlane.cpp
./System/Assets/Render/Mesh/MeshPlane.h
./System/Assets/Render/Mesh/MeshStatic.cpp
./System/Assets/Render/Mesh/MeshStatic.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\Render\\Material" FILES 
./System/Assets/Render/Material/MaterialBase.h
./System/Assets/Render/Material/SimpleMaterial.cpp
./System/Assets/Render/Material/SimpleMaterial.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\Render\\Components" FILES 
./System/Assets/Render/Components/RendererComponent.cpp
./System/Assets/Render/Components/RendererComponent.h
)

SOURCE_GROUP("Fregat\\System\\Assets\\AssetsManagement" FILES 
./System/Assets/AssetsManagement/AssetBase.h
./System/Assets/AssetsManagement/AssetBin.cpp
./System/Assets/AssetsManagement/AssetBin.h
./System/Assets/AssetsManagement/AssetsInfo.h
./System/Assets/AssetsManagement/AssetsManager.cpp
./System/Assets/AssetsManagement/AssetsManager.h
./System/Assets/AssetsManagement/AssetSys.h
)

# Creates a folder "libraries" and adds target project (math.vcproj) under it
set_property(TARGET Fregat PROPERTY FOLDER "libraries")

# Properties->General->Output Directory
# set_target_properties(Fregat PROPERTIES
#                       RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin)
					  
					  # Adds logic to INSTALL.vcproj to copy math.dll to the destination directory
# install (TARGETS Fregat
#          RUNTIME DESTINATION ${PROJECT_SOURCE_DIR}/_install
#          LIBRARY DESTINATION ${PROJECT_SOURCE_DIR}/_install)