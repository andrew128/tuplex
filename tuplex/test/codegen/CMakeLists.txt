CMAKE_MINIMUM_REQUIRED(VERSION 3.12 FATAL_ERROR)

# enable c++14
set(CMAKE_CXX_STANDARD 14)

file(GLOB SRCS *.cc)

include(GoogleTest)

ADD_EXECUTABLE(testcodegen ${SRCS})


TARGET_LINK_LIBRARIES(testcodegen
        libcodegen
        ${GTest_LIBRARIES}
        runtime
        )

gtest_add_tests(TARGET testcodegen TEST_PREFIX "")