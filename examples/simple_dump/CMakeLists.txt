# Assume this cmake is called from tinyusdz root(../../)
set(EXAMPLE_TARGET "simple_dump")

set(TINYUSDZ_SIMPLE_DUMP_SOURCES
    main.cc
    )

add_executable(${EXAMPLE_TARGET} ${TINYUSDZ_SIMPLE_DUMP_SOURCES})
add_sanitizers(${EXAMPLE_TARGET})

target_include_directories(${EXAMPLE_TARGET} PRIVATE ${PROJECT_SOURCE_DIR}/src)
target_link_libraries(${EXAMPLE_TARGET} tinyusdz_static)


set_target_properties(${EXAMPLE_TARGET} PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
