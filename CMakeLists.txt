cmake_minimum_required(VERSION 3.14)
project(my-project CXX)

if(NOT subgine-pkg AND NOT subgine-pkg-as-dependency)
	include("subgine-pkg-modules/default-profile.cmake")
endif()

add_library(my-lib lib.cpp)

find_package(kangaru 4.2 REQUIRED)
find_package(cpplocate REQUIRED)
find_package(Catch2 2.8 REQUIRED)

target_link_libraries(my-lib
PUBLIC
   kangaru

PRIVATE
   cpplocate::cpplocate
   Catch2::Catch2
)
