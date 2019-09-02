message( "INFO :: Calling CMake (version ${CMAKE_VERSION}) located at ${CMAKE_COMMAND}" )
message( "INFO :: Generating build files for project located at ${CMAKE_CURRENT_SOURCE_DIR}" )
message( "INFO :: Build files will be stored at :: ${CMAKE_CURRENT_BINARY_DIR}" )

cmake_minimum_required(VERSION 3.11)

project(02_simple_cmake
    VERSION # major.minor.patch.tweak
        1.0.0.0
    LANGUAGES
        CXX # Default
)

add_executable(hello_world hello_world.cxx)

message( "INFO :: New project created -> ${PROJECT_NAME} (version ${PROJECT_VERSION})" )

message( "VERBOSE :: Other variables" )
# CURRENT is important when the project is included as a subdirectory in another project
# Variables without CURRENT reference the top most project instead of the project currently being built by CMake
message( "VERBOSE :: CMAKE_BINARY_DIR           = ${CMAKE_BINARY_DIR}" )
message( "VERBOSE :: CMAKE_CURRENT_BINARY_DIR   = ${CMAKE_CURRENT_BINARY_DIR}" )
message( "VERBOSE :: 02_simple_cmake_BINARY_DIR = ${02_simple_cmake_BINARY_DIR}" )
message( "VERBOSE :: PROJECT_BINARY_DIR         = ${PROJECT_BINARY_DIR}" )
message( "VERBOSE :: CMAKE_SOURCE_DIR           = ${CMAKE_SOURCE_DIR}" )
message( "VERBOSE :: CMAKE_CURRENT_SOURCE_DIR   = ${CMAKE_CURRENT_SOURCE_DIR}" )
message( "VERBOSE :: 02_simple_cmake_SOURCE_DIR = ${02_simple_cmake_SOURCE_DIR}" )
message( "VERBOSE :: PROJECT_SOURCE_DIR         = ${PROJECT_SOURCE_DIR}" )
message( "VERBOSE :: CMAKE_PROJECT_NAME = ${CMAKE_PROJECT_NAME}" )
message( "VERBOSE :: PROJECT_NAME       = ${PROJECT_NAME}" )
message( "VERBOSE :: CMAKE_INCLUDE_PATH = ${CMAKE_INCLUDE_PATH}" )
message( "VERBOSE :: CMAKE_LIBRARY_PATH = ${CMAKE_LIBRARY_PATH}" )
message( "VERBOSE :: CMAKE_PREFIX_PATH  = ${CMAKE_PREFIX_PATH}" )
message( "VERBOSE :: CMAKE_CXX_COMPILER = ${CMAKE_CXX_COMPILER}" )
message( "VERBOSE :: CMAKE_CXX_FLAGS = ${CMAKE_CXX_FLAGS}" )

message( "INFO :: Build done :)" )
