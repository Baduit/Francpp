cmake_minimum_required(VERSION 3.0)

project(Francpp VERSION 1.0.0 DESCRIPTION "A simple header")


option(EXAMPLE "EXAMPLE" ON)

# The library
add_library(francpp INTERFACE)
target_sources(francpp INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src/Francpp.hpp)
target_include_directories(francpp INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src)

if (EXAMPLE)
	add_executable(example src/main.cpp)
	target_link_libraries(example francpp)
endif()

