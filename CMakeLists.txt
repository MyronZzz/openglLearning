cmake_minimum_required(VERSION 3.23)
project(openglLearning)

set(CMAKE_CXX_STANDARD 17)
add_compile_definitions()
find_package(OpenGL REQUIRED)

set(COMMON_HEADERS include/LoadShaders.h)
set(COMMON_SRC include/ include/glad/glad.c src/LoadShaders.cpp)
set(EXAMPLES
        1_1_Triangles
        )


foreach(EXAMPLE ${EXAMPLES})
    add_executable(${EXAMPLE} ${PROJECT_SOURCE_DIR}/src/${EXAMPLE}.cpp ${COMMON_HEADERS} ${COMMON_SRC} )
    include_directories("${PROJECT_SOURCE_DIR}/include")
    target_link_libraries(${EXAMPLE} ${PROJECT_SOURCE_DIR}/lib/libglfw3.a)
endforeach(EXAMPLE)


