project(PackageTest CXX)
cmake_minimum_required(VERSION 3.6)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_STATIC_LINKER_FLAGS "-Wl,--verbose")
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

find_package(Threads REQUIRED)

add_executable(example example.cpp)
target_link_libraries(example ${CONAN_LIBS} Threads::Threads)
