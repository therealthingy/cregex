cmake_minimum_required(VERSION 3.28)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 17)    # Required 4 `std::align_val_t`


project(cregex C CXX)


# -----------------------------------------------------------------------------
# CMake targets
# -----------------------------------------------------------------------------
add_library(${PROJECT_NAME} OBJECT)
target_sources(${PROJECT_NAME}
    PRIVATE
        src/cregex.cpp
    INTERFACE
        FILE_SET HEADERS
            TYPE HEADERS
            BASE_DIRS include/
)

option(BUILD_DEMO "CREGEX DEMO" OFF)
if (${BUILD_DEMO})
    add_executable(cregex-demo src/demo.c)
    target_link_libraries(cregex-demo PRIVATE cregex)
endif()
