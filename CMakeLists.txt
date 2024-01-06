cmake_minimum_required(VERSION 2.8.9...3.22)

project(libigl_demo)

include(D:/vcpkg/scripts/buildsystems/vcpkg.cmake)
# Maybe stop from CMAKEing in the wrong place

#find_package(libigl CONFIG REQUIRED)
find_package(libigl CONFIG REQUIRED)
INCLUDE_DIRECTORIES(${libigl_DIR})
INCLUDE_DIRECTORIES(${imgui_DIR})
INCLUDE_DIRECTORIES(${glad_DIR})
INCLUDE_DIRECTORIES(${glfw3_DIR})
INCLUDE_DIRECTORIES(${embree_DIR})

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR})

# Create an executable
add_executable(
		Example
        main.cpp
        )

target_link_libraries(Example PRIVATE igl::igl_xml igl::igl_core igl::igl_glfw igl::igl_imgui)