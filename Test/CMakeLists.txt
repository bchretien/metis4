# Build program.
add_executable(mtest mtest.c ../Programs/io.c)
target_link_libraries(mtest metis-4)
