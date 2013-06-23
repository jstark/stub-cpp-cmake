project(cbli)

set(SOURCES cbli.cpp)

add_executable(cbli ${SOURCES})
target_link_libraries(cbli cbl)	# link with cbl library