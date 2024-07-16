cmake_minimum_required(VERSION 3.3)
project(si_reader)

#Set custom cimpilers (C and C++)
set(CMAKE_C_COMPILER x86_64-w64-mingw32-gcc.exe)
set(CMAKE_CXX_COMPILER x86_64-w64-mingw32-g++.exe)

#Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

#Custom compiler flags
add_compile_options(-Wall -std=c++11 -Dunicode -DWIN32 -c)

#Include directories
include_directories(include)

#Source files
file(GLOB SOURCE "src/*.cpp")

#Add executable 
add_executable(si_reader WIN32 ${SOURCE})

#Link all
target_link_options(si_reader PRIVATE --static -municode)