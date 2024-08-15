cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

project(minisat)

#--------------------------------------------------------------------------------------------------
# Build Targets:

set(MINISAT_LIB_SOURCES
    minisat/utils/System.cc
    minisat/core/Solver.cc
    minisat/simp/SimpSolver.cc)

add_library(minisat-lib-static STATIC ${MINISAT_LIB_SOURCES})

set_target_properties(minisat-lib-static PROPERTIES OUTPUT_NAME "minisat")

target_compile_definitions(minisat-lib-static PRIVATE __STDC_FORMAT_MACROS __STDC_LIMIT_MACROS)
target_include_directories(minisat-lib-static PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
