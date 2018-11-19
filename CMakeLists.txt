cmake_minimum_required(VERSION 3.1)

set (CMAKE_CXX_STANDARD 11)

project(catch2_test)
find_package(Catch2 REQUIRED)
file(GLOB TEST_SOURCES "test_*.cpp")
add_executable(catch2_test ${TEST_SOURCES} )
set_target_properties(catch2_test PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/tests")
target_link_libraries(catch2_test Catch2::Catch2)
include(CTest)
include(ParseAndAddCatchTests)
ParseAndAddCatchTests(catch2_test)
