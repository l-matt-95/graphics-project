cmake_minimum_required(VERSION 3.27)
project(graphics-project)

set(CMAKE_CXX_STANDARD 17)

add_executable(graphics-project
        main.cpp
        glad.c
        AssimpImport.cpp
        Mesh3D.cpp
        Object3D.cpp
        ShaderProgram.cpp
        StbImage.cpp
)

find_package(SFML COMPONENTS system window REQUIRED)
find_package(GLM CONFIG REQUIRED)
find_package(ASSIMP REQUIRED)

include_directories(${CMAKE_SOURCE_DIR}/include)

target_link_libraries(graphics-project
        sfml-system sfml-window
        ${ASSIMP_LIBRARIES}
)
