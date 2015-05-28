# Build program.
add_executable(mtest mtest.c ../Programs/io.c)
target_link_libraries(mtest metis-4)

add_test(NAME run_tests
  COMMAND "mtest" "${CMAKE_SOURCE_DIR}/Graphs/4elt.graph"
  WORKING_DIRECTORY ${CMAKE_BINARY_DIR}/Test)
