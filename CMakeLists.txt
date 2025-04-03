cmake_minimum_required(VERSION 3.10)
project(MyOpenGLProject)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)

include_directories(
    include
)

file(GLOB SOURCES 
    "src/*.cpp"
)

file(GLOB GLAD_SOURCE "include/glad/*.c")

add_executable(${PROJECT_NAME} ${SOURCES} ${GLAD_SOURCE})

target_link_libraries(${PROJECT_NAME} OpenGL::GL)

target_link_libraries(${PROJECT_NAME} "${CMAKE_SOURCE_DIR}/lib/glfw3.lib")