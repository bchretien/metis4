# Build program.
add_executable(graphchk-4 graphchk.c io.c)
add_executable(pmetis-4 pmetis.c io.c)
add_executable(kmetis-4 kmetis.c io.c)
add_executable(oemetis-4 io.c oemetis.c smbfactor.c)
add_executable(onmetis-4 io.c onmetis.c smbfactor.c)
add_executable(mesh2dual-4 mesh2dual.c io.c)
add_executable(mesh2nodal-4 mesh2nodal.c io.c)
add_executable(partdmesh-4 partdmesh.c io.c)
add_executable(partnmesh-4 partnmesh.c io.c)

foreach(prog graphchk-4 pmetis-4 kmetis-4 oemetis-4 onmetis-4 mesh2dual-4 mesh2nodal-4 partdmesh-4 partnmesh-4 graphchk-4)
  target_link_libraries(${prog} metis-4)
endforeach(prog)

if(METIS_INSTALL_BIN)
  install(TARGETS graphchk-4 pmetis-4 kmetis-4 oemetis-4 onmetis-4 mesh2dual-4 mesh2nodal-4 partdmesh-4 partnmesh-4 graphchk-4
    RUNTIME DESTINATION bin)
endif()

