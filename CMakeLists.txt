cmake_minimum_required(VERSION 3.10)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON) # For clang-tidy
set(BUILD_SHARED_LIBS OFF) # we expect external libraries to be linked statically.
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_COMPILER_ID "Clang")
project (KopDB
         VERSION 2024.5
         DESCRIPTION "The Distributed Relational Database Management System"
         LANGUAGES C CXX
)

if (NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  message(STATUS "Setting build type to `Debug` as none was specified.")
  set(CMAKE_BUILD_TYPE "Debug")
endif


######################################################################################################################
# Other Cmake modules.
# Must be added after configuring compiler parameters. 
######################################################################################################################
add_subdirectory(tools)
add_subdirectory(src)
add_subdirectory(third_party)