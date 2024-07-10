cmake_minimum_required(VERSION 3.16 FATAL_ERROR)
project(STUB_PROJECT VERSION 0.1.0 LANGUAGES CXX)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)

include(MessageColors)
include(LoggingHelper)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/build/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/build/lib)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(CommonProjectOptions)
include(CompilerWarnings)

include(ClangTidy)
include(ClangFormat)
include(CTags)

add_subdirectory(src)

set(CPACK_GENERATOR "TGZ")
set(CPACK_PACKAGE_VENDOR "Glamhoth")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Application for passing controller input to Reentry via UDP.")
set(CPACK_PACKAGE_VERSION_MAJOR "0")
set(CPACK_PACKAGE_VERSION_MINOR "1")
set(CPACK_PACKAGE_VERSION_PATCH "0")

include(CPack)
