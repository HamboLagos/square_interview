project(tests)

# Build the googletest archives
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/gtest)
add_subdirectory(googletest)

# Add the gtest headers and compiled archives to the search path
include_directories(googletest/googletest/include/gtest)
include_directories(googletest/googlemock/include/gmock)
include_directories(${CMAKE_BINARY_DIR}/bin/gtest)

# Add source files to the search path
include_directories(${CMAKE_SOURCE_DIR}/src)
include_directories(${CMAKE_SOURCE_DIR}/utests)

# Build the tests
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/tests)
set(GTEST_LIBRARIES gmock gtest gmock_main)

include(tests.cmake)
