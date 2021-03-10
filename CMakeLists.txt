cmake_minimum_required(VERSION 3.0)

project(FrancppProject VERSION 1.0.0 DESCRIPTION "A simple header")


option(EXAMPLE "EXAMPLE" ON)

# The library
add_library(Francpp INTERFACE)
target_sources(Francpp INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src/Francpp/Francpp.hpp)
target_include_directories(Francpp INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src/Francpp)

if (EXAMPLE)
	add_executable(example src/example/main.cpp)
	target_link_libraries(example Francpp)
endif()

