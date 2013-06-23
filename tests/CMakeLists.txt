project(tests)

if(DEFINED GMOCK_ROOT)
	set(GMOCK_INCLUDE_DIR ${GMOCK_ROOT}/include)
	set(GMOCK_LIBRARIES ${GMOCK_ROOT}/lib/libgmock.a ${GMOCK_ROOT}/lib/libgmock_main.a)
else()
	message("GMOCK_ROOT is not defined")
	return()
endif()


if(DEFINED GTEST_ROOT)
	set(GTEST_INCLUDE_DIR ${GTEST_ROOT}/include)
	set(GTEST_LIBRARIES ${GTEST_ROOT}/lib/libgtest.a ${GTEST_ROOT}/lib/libgtest_main.a)
else()
	message("GTEST_ROOT is not defined")
	return()
endif()

include_directories(${GMOCK_INCLUDE_DIR})
include_directories(${GTEST_INCLUDE_DIR})

set(SOURCES all_tests.cpp)

add_executable(all_tests ${SOURCES})
target_link_libraries(all_tests cbl ${GMOCK_LIBRARIES} ${GTEST_LIBRARIES})