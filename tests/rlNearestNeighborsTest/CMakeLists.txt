find_package(Boost REQUIRED)

add_executable(
	rlNearestNeighborsTest
	iterator.h
	rlNearestNeighborsTest.cpp
	${rl_BINARY_DIR}/robotics-library.rc
)

if(MSVC AND CMAKE_CXX_COMPILER_VERSION VERSION_LESS 19.00.23918)
	target_compile_definitions(
		rlNearestNeighborsTest
		PUBLIC
		BOOST_ALL_NO_LIB
		BOOST_CHRONO_HEADER_ONLY
		BOOST_ERROR_CODE_HEADER_ONLY
		BOOST_SYSTEM_NO_DEPRECATED
	)
endif()

target_include_directories(
	rlNearestNeighborsTest
	PUBLIC
	${Boost_INCLUDE_DIR}
)

target_link_libraries(
	rlNearestNeighborsTest
	math
)

add_test(
	NAME rlNearestNeighborsTest
	COMMAND rlNearestNeighborsTest
)
