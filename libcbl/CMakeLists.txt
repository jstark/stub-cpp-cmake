project(libcbl)

set(SOURCES libcbl.cpp)

add_library(cbl SHARED ${SOURCES} ${CBL_HEADER})
