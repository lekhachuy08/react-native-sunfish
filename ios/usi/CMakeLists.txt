cmake_minimum_required(VERSION 2.8)

project(sunfish_usi CXX)

set(CMAKE_VERBOSE_MAKEFILE ON)

include(../Common.cmake)

include_directories("..")

add_subdirectory(../search "${CMAKE_CURRENT_BINARY_DIR}/search")
add_subdirectory(../book "${CMAKE_CURRENT_BINARY_DIR}/book")
add_subdirectory(../core "${CMAKE_CURRENT_BINARY_DIR}/core")
add_subdirectory(../common "${CMAKE_CURRENT_BINARY_DIR}/common")
add_subdirectory(../logger "${CMAKE_CURRENT_BINARY_DIR}/logger")

add_executable(sunfish_usi
    client/UsiClient.cpp
    client/UsiClient.hpp
    Main.cpp
)

target_link_libraries(sunfish_usi search)
target_link_libraries(sunfish_usi book)
target_link_libraries(sunfish_usi core)
target_link_libraries(sunfish_usi common)
target_link_libraries(sunfish_usi logger)
