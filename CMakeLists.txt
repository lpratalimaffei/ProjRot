project(ProjRot C)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -O3 -Wall")

add_library(ProjRotLibs
    ${PROJECT_SOURCE_DIR}/src/eigen2.c
    ${PROJECT_SOURCE_DIR}/src/eigen.c
    ${PROJECT_SOURCE_DIR}/src/nrutil.c
    ${PROJECT_SOURCE_DIR}/src/spline.c
    ${PROJECT_SOURCE_DIR}/src/invert_matrix3.c)

add_executable(RPHt.exe
    ${PROJECT_SOURCE_DIR}/src/main.c)
add_executable(RPHt2.exe
    ${PROJECT_SOURCE_DIR}/src/main2.c)

target_link_libraries(RPHt.exe ProjRotLibs m)
target_link_libraries(RPHt2.exe ProjRotLibs m)

install(TARGETS RPHt.exe DESTINATION bin)
install(TARGETS RPHt2.exe DESTINATION bin)
