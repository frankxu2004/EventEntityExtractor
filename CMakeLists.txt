project(EventEntityExtractor)
cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

file(GLOB_RECURSE sources *.cpp *.h)
file(GLOB_RECURSE data resources/*)

add_executable(JEE ${sources} ${data})

target_compile_options(JEE PUBLIC -std=c++11)
