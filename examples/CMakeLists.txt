file (COPY test-audio.wav DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

set (AUDIOFILE_EXAMPLE Example)

file (GLOB AUDIOFILE_EXAMPLES_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")
source_group (TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${AUDIOFILE_EXAMPLES_SOURCES})

add_executable (${AUDIOFILE_EXAMPLE} ${AUDIOFILE_EXAMPLES_SOURCES})
target_link_libraries (${AUDIOFILE_EXAMPLE} PUBLIC AudioFile)
target_compile_definitions (${AUDIOFILE_EXAMPLE} PUBLIC
  -D_USE_MATH_DEFINES # needed for M_PI macro
  -DPROJECT_BINARY_DIR="${CMAKE_CURRENT_BINARY_DIR}")