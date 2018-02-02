set (DOC_FILES
    scv/date03a2.pdf
    scv/scvref/vwg_1_0e.pdf
    scv/scv_random_white_paper4.pdf
    scv/intro_slides.pdf
    scv/scvref/vwg_1_0e.pdf
    )

foreach (DOC_FILE ${DOC_FILES})
  get_filename_component (DOC_INSTALL_PATH ${DOC_FILE} PATH)
  install (FILES ${DOC_FILE}
           DESTINATION ${CMAKE_INSTALL_DOCDIR}/${DOC_INSTALL_PATH}
           COMPONENT doc)
endforeach (DOC_FILE ${DOC_FILES})

# if (BUILD_SOURCE_DOCUMENTATION)
#   find_package (Doxygen REQUIRED)
#   add_custom_target (doxygen ALL
#                      DEPENDS doxygen-scv)

#   # SystemC source code documentation
#   set (PACKAGE_NAME ${PROJECT_NAME})
#   string(TOLOWER "${PROJECT_NAME}" PACKAGE_TARNAME)
#   set (PACKAGE_VERSION ${SCV_VERSION})
#   set (top_srcdir ${CMAKE_SOURCE_DIR})

#   configure_file (${CMAKE_CURRENT_SOURCE_DIR}/scv/doxygen/Doxyfile.in
#                   ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/Doxyfile @ONLY)
#   if (NOT EXISTS ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html)
#     file (MAKE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html)
#   endif (NOT EXISTS ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html)
#   set_source_files_properties (${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html
#                                PROPERTIES GENERATED 1)
#   add_custom_command (OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html/index.html
#                       COMMAND ${DOXYGEN_EXECUTABLE} ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/Doxyfile
#                       DEPENDS scv
#                       WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen
#                       COMMENT "Building the SCV source code documentation using Doxygen.")
#   add_custom_target (doxygen-scv
#                      DEPENDS ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html/index.html)
#   install (DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/html
#            DESTINATION ${CMAKE_INSTALL_DOCDIR}/scv/doxygen
#            COMPONENT doc)
#   install (FILES ${CMAKE_CURRENT_BINARY_DIR}/scv/doxygen/${PACKAGE_TARNAME}.tag
#            DESTINATION ${CMAKE_INSTALL_DOCDIR}/scv/doxygen
#            COMPONENT doc)

#   # TLM source code documentation
# endif (BUILD_SOURCE_DOCUMENTATION)
