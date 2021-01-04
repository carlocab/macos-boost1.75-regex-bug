cmake_minimum_required(VERSION 3.19)

project(foo LANGUAGES "CXX")

set(Boost_USE_STATIC_LIBS ON)
find_package(Boost 1.75 REQUIRED COMPONENTS graph)

add_library(foo SHARED foo.cpp)
target_include_directories(foo PRIVATE ${Boost_INCLUDE_DIRS})
target_link_libraries(foo PRIVATE ${Boost_LIBRARIES})
