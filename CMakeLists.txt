# https://www.glfw.org/docs/latest/build_guide.html#build_link_cmake_source
# https://github.com/Dav1dde/glad/issues/186
cmake_minimum_required(VERSION 3.21.2)

project(tamachan)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(external/glfw)
add_subdirectory(external/glad)

add_executable(tamachan tamachan.cpp)
target_link_libraries(tamachan PUBLIC glfw PRIVATE glad)
