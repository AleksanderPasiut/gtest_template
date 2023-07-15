cmake_minimum_required(VERSION 3.10)
project(gtest_template)

add_executable(${PROJECT_NAME} src/main.cpp)

add_dependencies(${PROJECT_NAME} gtest)
add_subdirectory(src/googletest)

target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR})
target_link_libraries(${PROJECT_NAME} PRIVATE -lstdc++)
target_link_libraries(${PROJECT_NAME} PRIVATE -lm)
target_link_libraries(${PROJECT_NAME} PRIVATE -lpthread)

link_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_BINARY_DIR}/lib)
target_link_libraries(${PROJECT_NAME} PRIVATE gtest)
target_link_libraries(${PROJECT_NAME} PRIVATE gtest_main)

