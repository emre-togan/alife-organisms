cmake_minimum_required(VERSION 3.16)
project(digital_organisms LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Catch2 3 REQUIRED)

enable_testing()
add_executable(tests tests/test_smoke.cpp)
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)
target_compile_options(tests PRIVATE -Wall -Wextra -Wpedantic)
add_test(NAME tests COMMAND tests)