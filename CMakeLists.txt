cmake_minimum_required(VERSION 3.22)

project(logic_circuit_simulator LANGUAGES CXX)

add_executable(lcs_app
    ${CMAKE_CURRENT_SOURCE_DIR}/app/main.cpp
)

find_package(GTest REQUIRED)
enable_testing()
include(GoogleTest)

add_executable(lcs_tests
    ${CMAKE_CURRENT_SOURCE_DIR}/tests/single_component_tests.cpp
)

target_link_libraries(lcs_tests PRIVATE
    GTest::gtest_main
)

gtest_discover_tests(lcs_tests)
