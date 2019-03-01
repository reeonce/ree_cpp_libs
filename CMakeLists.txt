cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)

project(ree_cpp_libs CXX)

option(REE_LIBS_ENABLE_SAMPLE "enable samples" OFF)
option(REE_LIBS_ENABLE_TESTS "enable unit tests" OFF)

if(REE_LIBS_ENABLE_SAMPLE)
    set(REE_IMAGE_ENABLE_SAMPLE ON CACHE BOOL "" FORCE)
endif(REE_LIBS_ENABLE_SAMPLE)

if(REE_LIBS_ENABLE_TESTS)
    set(REE_IMAGE_ENABLE_TESTS ON CACHE BOOL "" FORCE)
    set(REE_IO_ENABLE_TESTS ON CACHE BOOL "" FORCE)
endif(REE_LIBS_ENABLE_TESTS)

add_subdirectory(ree_unittest)
add_subdirectory(ree_io)
add_subdirectory(ree_image)

if(REE_LIBS_ENABLE_SAMPLE)
    add_subdirectory(ree_unittest_sample)
endif(REE_LIBS_ENABLE_SAMPLE)