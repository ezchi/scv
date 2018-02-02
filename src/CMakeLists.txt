
add_subdirectory(cudd)

###############################################################################
# Build rules for SCV library
###############################################################################
add_library (scv
    scv/scv_tr.cpp
    scv/scv_constraint.cpp
    scv/scv_constraint_range.cpp
    scv/scv_random.cpp
    scv/scv_init_seed.cpp
    scv/scv_util.cpp
    scv/scv_report.cpp
    scv/scv_debug.cpp
    scv/scv_expression.cpp
    scv/scv_introspection.cpp
    scv/scv_tr_text.cpp
    scv.h
    scv/scv_object_if.h
    scv/_scv_ext_rw.h
    scv/_scv_introspection.h
    scv/scv_sparse_array.h
    scv/_scv_list_iter.h
    scv/scv_random.h
    scv/_scv_ext_type.h
    scv/scv_util.h
    scv/_scv_smart_ptr.h
    scv/scv_introspection.h
    scv/scv_tr.h
    scv/scv_kit_date.h
    scv/scv_report.h
    scv/scv_bag.h
    scv/_scv_ext_util.h
    scv/_scv_ext_rand.h
    scv/_scv_ext_comp.h
    scv/_scv_data_structure.h
    scv/scv_expression.h
    scv/scv_shared_ptr.h
    scv/scv_constraint.h
    scv/scv_messages.h
    scv/_scv_randomization.h
    scv/_scv_associative_array.h
    scv/scv_constraint_range.h
    scv/scv_debug.h
    scv/scv_ver.h
    scv/_scv_ext_callbacks.h
    $<TARGET_OBJECTS:cuddobj>
    $<TARGET_OBJECTS:cudd>
    $<TARGET_OBJECTS:st>
    $<TARGET_OBJECTS:dddmp>
    $<TARGET_OBJECTS:mnemosyne>
    $<TARGET_OBJECTS:nanotrav>
    $<TARGET_OBJECTS:mtr>
    $<TARGET_OBJECTS:util>
    )

target_include_directories(scv
    PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
    )

target_include_directories(scv
    PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}/cudd/2.3.0/cudd
    ${CMAKE_CURRENT_LIST_DIR}/cudd/2.3.0/obj
    ${CMAKE_CURRENT_LIST_DIR}/cudd/2.3.0/mtr
    )

target_link_libraries (scv PUBLIC SystemC::systemc)

set_target_properties (scv
    PROPERTIES
    LINKER_LANGUAGE CXX)


# ###############################################################################
# # Install rules for SCV library
# ###############################################################################
install (TARGETS scv EXPORT scvTargets
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    COMPONENT lib)

# # Install the SCV
install(FILES
    scv.h
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
    )
install(DIRECTORY ./scv
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
    FILES_MATCHING PATTERN "*.h"
    )
